
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
}
ul, ol {
  direction: rtl;
  text-align: right;
  padding-right: 2em;
  padding-left: 0;
}
li {
  text-align: right;
}
/* Fix checkbox alignment in RTL */
input[type="checkbox"] {
  margin-left: 0.5em;
  margin-right: 0;
  float: right;
  clear: right;
}
.task-list-item {
  direction: rtl;
  text-align: right;
}
.task-list-item input {
  margin-left: 0.5em;
  margin-right: 0;
}
table {
  direction: rtl;
  text-align: right;
  width: 100%;
  border-collapse: collapse;
}
th, td {
  text-align: right;
  padding: 8px;
  border: 1px solid #ddd;
  vertical-align: top;
}
th {
  background-color: #f2f2f2;
  font-weight: bold;
}
</style>

<div dir="rtl" style="text-align: right;">

# SECURITY_CHECKLIST_TEMPLATE.he.md

מסמך זה נועד לשמש כתבנית רשמית לבדיקות אבטחה כחלק מתהליך הפיתוח.  
הוא משתלב בשכבת ה־Validation של Docs-as-System, ומסמן באופן ברור מה נבדק ע"י הסוכן, מה דורש אישור אנושי, ומה נבדק בשילוב ביניהם.

**קבצים קשורים:**  
`COMPLIANCE_POLICY.md` | `AGENT_OPERATIONAL_POLICY.md` | `IMPLEMENTATION_LOG.md`

---

## מדריך קצר

| סוג | משמעות | מבצע |
|------|---------|--------|
| AUTO | נבדק אוטומטית ע"י הסוכן (Agent) | סוכן |
| HUMAN | נדרש שיקול דעת ואישור אנושי בלבד | אדם |
| HYBRID | נבדק ע"י הסוכן אך דורש גם אישור אנושי | שניהם |

הקובץ מתעדכן בכל שינוי קוד, תצורה או תהליך פריסה.  
לפני כל Merge לסביבה ראשית – יש לוודא שכל סעיף רלוונטי סומן כ"בוצע".

---

## 1. גישה והרשאות

| סוג | סעיף | סטטוס | הוכחה / הערה |
|------|-------|---------|---------------|
| AUTO | אין סודות או סיסמאות בקוד (סריקה ע"י Agent) | | |
| AUTO | בקרות גישה קיימות בקוד (Authorization) | | |
| HYBRID | רק משתמשים נדרשים מחזיקים הרשאות ל־DB / שירותים | | |
| HUMAN | בוצעה סקירה ידנית של הרשאות אדמין לפני פריסה | | |

---

## 2. נתונים רגישים

| סוג | סעיף | סטטוס | הוכחה / הערה |
|------|-------|---------|---------------|
| AUTO | מידע אישי לא נכתב ללוגים | | |
| AUTO | תקשורת בין שירותים משתמשת בהצפנה (HTTPS / TLS) | | |
| HYBRID | קבצי קונפיגורציה לא מכילים מידע רגיש | | |
| HUMAN | נבדקה ידנית מדיניות שמירת נתונים | | |

---

## 3. קלטים ו־API

| סוג | סעיף | סטטוס | הוכחה / הערה |
|------|-------|---------|---------------|
| AUTO | כל קלט עובר בדיקת ולידציה בסיסית | | |
| AUTO | שימוש בפרמטרים מאובטחים ב־SQL / ORM | | |
| HYBRID | Endpoint חיצוניים מוגנים באימות מתאים | | |
| HUMAN | נבדקה ידנית התנהגות API חריגה או מסוכנת | | |

---

## 4. תלותים (Dependencies)

| סוג | סעיף | סטטוס | הוכחה / הערה |
|------|-------|---------|---------------|
| AUTO | סריקת פגיעויות בספריות | | |
| AUTO | קובץ נעילת גרסאות קיים (`package-lock.json` / `csproj` נעול) | | |
| HYBRID | תיעוד ספריות חדשות עודכן | | |
| HUMAN | רישיונות ספריות נבדקו ידנית | | |

---

## 5. לוגים וניטור

| סוג | סעיף | סטטוס | הוכחה / הערה |
|------|-------|---------|---------------|
| AUTO | לוגים אינם מכילים מידע אישי או סודי | | |
| HYBRID | אירועים חשובים (גישה, חריגה, ניסיון כשל) נרשמים | | |
| HUMAN | הוגדרו כללים לזיהוי פעילות חריגה (Alerts) | | |

---

## 6. פריסה ו־CI

| סוג | סעיף | סטטוס | הוכחה / הערה |
|------|-------|---------|---------------|
| AUTO | קובצי Build לא מכילים Secrets | | |
| HYBRID | תהליך הפריסה רץ עם הרשאות מינימליות | | |
| HUMAN | נבדקה ידנית סביבת ה־Production לפני פריסה | | |

---

## 7. סוכני AI ו־LLM

| סוג | סעיף | סטטוס | הוכחה / הערה |
|------|-------|---------|---------------|
| AUTO | הסוכן לא שולח מידע רגיש למודלים חיצוניים | | |
| HYBRID | פעולות הסוכן מתועדות בלוגים ייעודיים | | |
| HUMAN | בוצעה בדיקה ידנית לתשומות ותוצרים של הסוכן | | |

---

## חריגים (Exceptions)

כל חריג מחייב אישור אנושי מפורש.

| סעיף | תיאור החריג | סיכון | מי אישר | תאריך תוקף | הערות |
|--------|---------------|---------|-------------|-----------|---------|

---

## חתימות

| תפקיד | שם | תאריך | הערות |
|--------|------|---------|----------|
| סוכן |  |  |  |
| מאשר אנושי |  |  |  |

---

**הנחיה אחרונה:**  
אין לראות בקובץ זה מסמך רגולטורי, אלא מנגנון תיעוד שמאפשר לצוות לפתח בביטחון, בשקיפות ובשיתוף בין אדם לסוכן.


---

© 2025 תומר קדם. חלק ממערך התבניות הרשמי של **Docs-as-System**.

</div>
