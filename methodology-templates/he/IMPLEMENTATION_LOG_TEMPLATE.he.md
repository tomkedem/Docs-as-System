
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
table {
  direction: rtl;
  text-align: right;
}
th, td {
  text-align: right;
}
</style>

<div dir="rtl" style="text-align: right;">
# IMPLEMENTATION_LOG_TEMPLATE.he.md

**סוג מסמך:** יומן יישום ותיעוד  
**מטרה:** לאפשר תיעוד אוטומטי, עקבי וברור של פעולות הפיתוח, כפי שהן נאספות ישירות מ־PR, CI, Commitים ולוגי הסוכן.  
**קבצים קשורים:** `AGENT_OPERATIONAL_POLICY.md`, `HUMAN_OPERATIONAL_POLICY.md`, `SECURITY_CHECKLIST.md`, `VALIDATION_REPORT.md`

---

## 1. עקרון פעולה

`IMPLEMENTATION_LOG.md` נוצר ומתעדכן באופן אוטומטי על ידי הסוכן בזמן אמת,  
בהתבסס על מידע ממערכת ניהול הגרסאות (Git), מתהליכי CI, ומביקורות קוד (PR).  

האדם לא נדרש למלא דבר ידנית — רק לאשר, לתקן או להוסיף הבהרה במקרה הצורך.

---

## 2. מבנה הרשומה האוטומטית

כל פעולה או שינוי מתועדים באופן אוטומטי במבנה אחיד:

| שדה | תיאור |
|------|---------|
| **תאריך** | נלקח אוטומטית ממועד ה־Commit או ה־PR |
| **מזהה פעולה** | נוצר ע"י הסוכן (למשל `IMP-2025-0012`) |
| **סוג פעולה** | Commit / PR / Test / Review / Merge / Deploy |
| **מקור** | שם הענף או הריצה (branch / pipeline) |
| **מצב בדיקות** | Passed / Warning / Failed / Need Human Review |
| **ביצע** | סוכן / אדם / משולב |
| **אישור אנושי** | שם המאשר או תגובה ב־PR |
| **הערות** | טקסט קצר במידת הצורך (למשל “תיקון בעקבות ממצא אבטחה”) |

---

## 3. דוגמה לרשומה אוטומטית

```markdown
## 2025-11-11 14:32
ID: IMP-2025-0045  
Action: Commit  
Source: feature/logging_cleanup  
Status: Passed  
Executed by: Agent  
Human Review: Approved by Tomer Kedem (PR-#142)  
Notes: Removed redundant logging from service layer

## 4. מקורות הנתונים

| מקור | מה נאסף ממנו |
|---|---|
| Git Commit | מזהה commit, תקציר diff, כותב, תאריך |
| Pull Request | הערות מאשרים, סטטוס checks, תוצאות בדיקות |
| CI Pipeline | סטטוס Build/Test/Security scan |
| Agent Runtime | פעולות אוטומטיות, ממצאי self-check, חריגות |

> הסוכן מאחד את המידע לרשומה אחת ומוסיף אותה ללוג מבלי לשנות רשומות קיימות.

---

## 5. חריגות ופעולות מתוקנות

כאשר הסוכן מזהה כשל, מדיניות חריגה או צורך בתיקון, נוצרת רשומת Exception אוטומטית:

```markdown
## Exception
Time: 2025-11-11 15:04
Event: security_scan_failed
Auto-pause: yes
Assigned to: Human Approver
Resolution: updated dependency version
Result: Passed after retry


</div>  
