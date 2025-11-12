
> ⚙️ **Template Notice:**  
> This file is part of the official Docs-as-System MethodologyTemplates.  
> Do not edit directly inside the project – copy it to `/docs/` when initializing a new system.
<style>
body {
  direction: rtl;
  text-align: right;
}
.markdown-body {
  direction: rtl;
  text-align: right;
}
h1, h2, h3, h4, h5, h6 {
  text-align: right;
}
p, li, blockquote {
  text-align: right;
<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

}
ul, ol {
  direction: rtl;
  text-align: right;
<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

  padding-right: 2em;
  padding-left: 0;
}
li {
  text-align: right;
}
table {
  direction: rtl;
  text-align: right;
}
th, td {
  text-align: right;
}
</style>


<div dir="rtl" style="text-align: right;">

# תבנית מדיניות פעולה לסוכן (Agent Operational Policy)

**מסמך:** `AGENT_OPERATIONAL_POLICY.md`  
**קובץ תצורה נלווה:** `AGENT_CONFIG.yaml`  
**יוצר:** אדם (בהתאם למדיניות הארגון)  
**מאשר:** ארכיטקט ראשי / מנהל אבטחה / Tech Lead  
**סוג אפיון:** מדיניות פעולה  

**מטרה:** להגדיר את אופן הפעולה, הבקרה, והתיעוד של סוכן ה־AI הפועל בפרויקט.  
המסמך מוודא שכל פעולה של הסוכן ניתנת להסבר, לשחזור ולבקרה אנושית.

---

## עקרונות יסוד

1. הסוכן פועל **רק על בסיס מסמכים מאושרים** (`PROJECT_SPEC`, `ARCHITECTURE_BLUEPRINT`, `PLAN.md`).  
2. כל שינוי שהסוכן מבצע נרשם ביומן המימוש (`IMPLEMENTATION_LOG.md`).  
3. הסוכן **אינו כותב ישירות לענף מוגן** (`main`, `release`) אלא משתמש בסניף עבודה (`agent-workspace`).  
4. כל תוצר של הסוכן נבדק ונחתם בתג `HUMAN_APPROVED` לאחר ביקורת אנושית.  
5. במקרי אי־ודאות או סתירה בין מסמכים – הסוכן עוצר עבודה ומבקש הנחיה חדשה.

---

## מדיניות עבודה

| תחום | עקרונות פעולה |
|------|----------------|
| **כתיבת קוד** | כתיבה מבוססת הגדרות, שמירה על שמות עקביים, הימנעות מקוד לא מוסבר. |
| **תיעוד** | כל שינוי בקוד מלווה בעדכון במסמך הרלוונטי (Spec / Blueprint). |
| **Commit** | הסוכן מבצע Commits קטנים וממוקדים, עם הודעת commit תיאורית באנגלית. |
| **בדיקות** | כל שינוי מלווה בהרצת Self-Check אוטומטי ובדיווח תוצאות. |
| **שגיאות** | במקרה של כשל או שגיאה לוגית – הסוכן מתעד את השגיאה ומפסיק פעולה עד הנחיה. |

---

## מדיניות אבטחה וכתיבת קוד מאובטח (Security & Secure Coding)

הסוכן פועל בהתאם לעקרונות אבטחת מידע בסיסיים שנועדו להגן על המערכת, הקוד והמידע הארגוני.

### עקרונות פעולה

- **אין שימוש במפתחות, סיסמאות או אסימוני גישה (Tokens) בקוד גלוי.**  
  יש להשתמש במשתני סביבה או בקובצי קונפיגורציה מאובטחים בלבד.

- **ולידציה קלטים (Input Validation):**  
  בכל קוד שיוצר או מתוקן ע"י הסוכן נדרשת בדיקה שהקלט עובר ולידציה בסיסית לפני עיבוד.

- **הימנעות מהזרקות (Injection Safety):**  
  כל גישה למסד נתונים או להרצת פקודות משתמשת בפרמטרים ולא במחרוזות דינמיות.

- **שמירה על Least Privilege:**  
  הקוד שנוצר לא מניח הרשאות מנהל, אלא גישה מינימלית בלבד לפעולה הדרושה.

- **שמירה על פרטיות מידע:**  
  אין לכתוב ללוגים או למסמכים מידע מזהה אישי, סיסמאות, או טוקנים.  
  אם יש צורך בבדיקת נתונים רגישים – הם נחתכים או מוצפנים.

- **תיעוד אבטחתי:**  
  כל שינוי שקשור לאבטחה מתועד ב־`IMPLEMENTATION_LOG.md` עם התג `SECURITY_CHANGE`.

- **בדיקות Self-Security:**  
  לפני כל Commit הסוכן בודק שאין קריאות בלתי מבוקרות, כתיבה ישירה לקבצים חיצוניים, או שדות רגישים בקוד.

---

**הערה:**  
מומלץ שבכל פרויקט יהיה גם `SECURITY_CHECKLIST.md` נלווה, שבו מפורטים הכללים המיוחדים לאותו ארגון או מוצר.
 
--- 

## מבנה Commit תקין

כל commit של הסוכן יכיל:

- תיאור קצר וברור של הפעולה.  
- קישור למסמך רלוונטי (למשל: `PROJECT_SPEC.md § Use Case 2`).  
- מזהה משימה (אם קיים ב־`PLAN.md`).  
- תג אחד לפחות:  
  - `‏AI_GENERATED` – נוצר ע"י סוכן  
  - `‏HUMAN_APPROVED` – אושר ע"י אדם  
  - `‏VALIDATED` – נבדק לאחר Self-Check  

**דוגמה:**
feat: הוספת בדיקת Idempotency ל־BillingConsumer
Refs: PROJECT_SPEC.md §3.4 / PLAN.md #Task-12
Tags: AI_GENERATED


---

## מדיניות תיעוד

- כל שינוי נרשם ביומן `IMPLEMENTATION_LOG.md` עם תאריך, מזהה Commit, ותיאור קצר.  
- אם הסוכן עדכן מסמך קיים, עליו לוודא שהמבנה נשמר (כותרות, טבלאות, קישורים).  
- במידה והסוכן יצר קובץ חדש – עליו להוסיף הערת מקור:  
  `> נוצר ע"י סוכן AI על פי הנחיות האדם בתאריך ...`

---

## בקרת איכות פנימית (Self-Validation)

לפני כל Commit או Pull Request, הסוכן מבצע בדיקה עצמית:

1. בדיקת תקינות קוד (קומפילציה / Lint).  
2. בדיקת עקביות בין קוד למסמכים.  
3. בדיקת שמירת תגיות ופורמט Markdown.  
4. בדיקה שה־Commit כולל קישור למסמכי מקור.  
5. בדיקת שמירה על כללי מדיניות (`agent-workspace`, `AI_GENERATED`, `IMPLEMENTATION_LOG.md`).

אם אחת מהבדיקות נכשלת – הסוכן מתעד את הכשל (`VALIDATION_FAILED`) ומפסיק פעולה.

---

## טיפול בחריגות

- במקרה של שגיאת קוד, כשל Git או הוראה לא ברורה – הסוכן מסמן את הסטטוס `PENDING_REVIEW`.  
- במקרים חוזרים, הסוכן מפיק דוח Self-Diagnosis קצר המפרט את סוגי החריגות.  
- אין להמשיך תהליך אוטומטי ללא אישור אדם.

---

## תיעוד עקביות בין מסמכים

הסוכן שומר על עקביות בין:

| קשר בין קבצים | מה נבדק |
|----------------|----------|
| BUSINESS_REQUIREMENTS → PROJECT_SPEC | שמירה על מבנה ותכולה תואמים לכוונה העסקית |
| PROJECT_SPEC → ARCHITECTURE_BLUEPRINT | תאימות בין תיאור לוגי לארכיטקטורה |
| ARCHITECTURE_BLUEPRINT → IMPLEMENTATION_LOG | תאימות בין תכנון לביצוע בפועל |
| COMPLIANCE_POLICY / AGENT_OPERATIONAL_POLICY | שמירה על עקביות תהליכית וכללי פעולה |

---

## דוגמת זרימת עבודה טיפוסית

1. האדם מאשר סעיף חדש ב־`PROJECT_SPEC.md`.  
2. הסוכן יוצר קוד רלוונטי (`WebhookReceiver.cs`) ומעדכן את ה־Blueprint.  
3. הסוכן מוסיף רשומה ל־`IMPLEMENTATION_LOG.md` עם תג `AI_GENERATED`.  
4. האדם מבצע Review ומוסיף תג `HUMAN_APPROVED`.  
5. התוצאה נחתמת עם `VALIDATED` לאחר בדיקות מוצלחות.

---

## סיכום

המדיניות מבטיחה שכל פעולה של הסוכן ניתנת למעקב, אימות והסבר.  
המטרה היא לא “לפקח” על הסוכן, אלא לאפשר לו לפעול בביטחון בתוך מערכת חיה ומתועדת,  
שבה כל שינוי – קטן כגדול – נשמר כחלק מהידע המתמשך של הפרויקט.

---

© 2025 תומר קדם. חלק ממערך התבניות הרשמי של **Docs-as-System**.

</div>
