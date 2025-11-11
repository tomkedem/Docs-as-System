<div dir="rtl" style="text-align: right;">

# הגדרות סוכן

**קובץ:** `AGENT_CONFIG.yaml`  
**יוצר:** אדם (בהתאם למדיניות הארגון)  
**מאשר:** ארכיטקט ראשי / מנהל אבטחה / Tech Lead  
**סוג אפיון:** קובץ תצורה  

---

## הערת פתיח – שימוש אוניברסלי  

מסמך זה הוא חלק ממערך תבניות גנרי של **הפרויקט המתועד**  
ומשמש בסיס לתיעוד, בקרה ופיתוח בכל תחום תוכנה –  
Web, Mobile, Backend, Cloud, Data, AI, Embedded או Multi-Agent.  

התבנית מניחה מודל עבודה שבו הסוכן (AI) הוא המבצע בפועל  
והאדם הוא בעל הסמכות, האישור והבקרה.  
הסוכן פועל תחת מדיניות מתועדת, מתעד כל פעולה,  
ומבצע Commits מקומיים בלבד במערכת ניהול גרסאות (Git או דומה).  
האדם מאשר את השינויים ומבצע את ה-Merge הסופי.  

**עקרון היסוד:**  
הסוכן מיישם → האדם מאשר → Git שומר את האמת.

---

## מטרת הקובץ  

להגדיר את גבולות האחריות, רמות הגישה, תחומי הפעולה והבקרה של הסוכן.  
הקובץ נועד להבטיח שהסוכן פועל בבטחה, תחת פיקוח ובשקיפות מלאה כלפי האדם שמנהל את הפרויקט.  

הוא מגן על איכות, עקביות ואחריות אנושית,  
ומונע מהסוכן לבצע פעולות שאינן מאושרות מראש.

---

## מבנה קובץ לדוגמה  

(הערכים שלהלן משמשים כתבנית – יש להתאים בכל פרויקט לפי הצורך)
</div>  
<div dir="ltr" style="text-align: left;">

```yaml
# ===============================================
# AGENT CONFIGURATION TEMPLATE
# ===============================================

agent:
  id: "DEV-AGENT-001"
  name: "Development Assistant Agent"
  version: "1.0.0"
  role: "AI Development Partner"
  description: "Assists in documentation, code generation, validation, and monitoring under human supervision."
  active: true

permissions:
  # קבצים שבהם מותר לסוכן לעבוד
  allowed_paths:
    - "/docs/"
    - "/src/"
    - "/tests/"
    - "/scripts/automation/"
  
  # קבצים שבהם אסור לסוכן לשנות דבר
  restricted_paths:
    - "/config/security/"
    - "/prod-secrets/"
    - "/infra/deployment/"

  # סוגי קבצים מותרים לעריכה
  allowed_extensions:
    - ".cs"
    - ".py"
    - ".js"
    - ".sql"
    - ".md"
    - ".yaml"

  # הגבלת פעולות
  operations:
    read: true
    write: true
    delete: false
    execute: false

  # רמות גישה
  access_levels:
    system_config: "read-only"
    source_code: "read-write"
    documentation: "full"
    database: "read-only"

workflow:
  # פעולות שהסוכן רשאי לבצע כחלק מתהליך הפיתוח
  can_generate:
    - "code templates"
    - "api documentation"
    - "unit tests"
    - "data flow diagrams"
  can_review:
    - "code style"
    - "architecture consistency"
    - "security checklist"
  must_request_approval_for:
    - "code merges"
    - "production deployment"
    - "config updates"

monitoring:
  # רמת ניטור ואופן תיעוד פעולות הסוכן
  activity_logging: "full"
  log_format: "structured-json"
  report_frequency: "daily"
  validation_required: true

version_control:
  system: "git"                     # ניתן להחליף במערכת אחרת אם נדרש
  repository_path: "/repo/"
  agent_branch: "agent-workspace"   # סניף עבודה ייעודי לסוכן
  protected_branches:
    - "main"
    - "release"
  operations:
    allow_commit_local: true        # הסוכן רשאי לבצע Commits מקומיים בלבד
    allow_merge: false              # אין Merge ישיר לסניפים מוגנים
    require_human_review: true      # כל שינוי עובר ביקורת ואישור אנושי
  tagging_conventions:
    - AI_GENERATED
    - HUMAN_APPROVED
    - VALIDATED
  traceability:
    commit_linking: true            # כל Commit מקושר למשימה ב-PLAN ול-IMPLEMENTATION_LOG
    timestamped: true               # כל פעולה נחתמת בזמן ובזהות סוכן

limits:
  # מגבלות כלליות על פעילות הסוכן
  max_concurrent_tasks: 3
  max_edit_lines_per_file: 200
  idle_timeout_minutes: 15

communication:
  # הגדרות תקשורת עם צוות אנושי
  notify_channels:
    - "email"
    - "slack"
  escalation_policy:
    - condition: "unapproved change"
      action: "alert-human"
    - condition: "security violation"
      action: "immediate-lock"

compliance:
  # עקרונות מדיניות שעל הסוכן לפעול לפיהם
  follows_documents:
    - "COMPLIANCE_POLICY.md"
    - "ARCHITECTURE_BLUEPRINT.md"
    - "PLAN.md"
  human_final_approval: true
  ethics_enabled: true
  explainability_required: true

metadata:
  last_updated: "YYYY-MM-DD"
  updated_by: "Human Architect"
  notes: "Template configuration – adjust before project start."

```
</div>
<div dir="rtl" style="text-align: right;">

## עקרונות פעולה

- כל קובץ שעליו הסוכן עובד נשמר ב-Repository יחיד עם היסטוריית Commit מלאה.  
- כל שינוי נרשם בלוג פעולות (`IMPLEMENTATION_LOG.md`) ומחייב Review אנושי לפני מיזוג.  
- תגיות (Tags) ו-Metadata מספקות עקיבות מלאה בין Commit ← משימה ← בדיקה ← אישור.  
- אין ביצוע פעולות Git מסוכנות (Force Push / Delete Branch / Rewrite History).  
- ‏Git משמש כאן לא רק ככלי ניהול קוד, אלא כשכבת **חתימה ואחריות מערכתית** של הפרויקט כולו.  

---

## עקרונות הפעלה כלליים

1. **שקיפות מלאה** – כל פעולה מתועדת אוטומטית.  
2. **אחריות אנושית** – אין ביצוע פעולות קריטיות ללא אישור.  
3. **איסור פעולה עצמאית** – הסוכן לעולם אינו מבצע ‏Deploy, ‏Merge או שינוי אבטחה בעצמו.  
4. **הקשר מתועד** – כל פעולה חייבת להיות משויכת למשימה קיימת (`PLAN.md` או `IMPLEMENTATION_LOG.md`).  
5. **ניטור תמידי** – כל שינוי נבדק ע"י סוכן נוסף או מנגנון Audit אנושי.  

---

## דוגמת תהליך עבודה (Flow Example)

1. אדם יוזם משימה חדשה ב-`PLAN.md`.  
2. הסוכן קורא את המשימה ומייצר טיוטת קוד / תיעוד.  
3. הפעולה נרשמת אוטומטית ב-`IMPLEMENTATION_LOG.md`.  
4. אדם בוחן את השינוי ומבצע ‏Review.  
5. רק לאחר אישור, הפעולה משולבת במערכת.  

---

## Agent Collaboration Note

קובץ זה מגדיר את כללי שיתוף הפעולה **אדם–סוכן**.  
הוא קובע במפורש:  

- היכן הסוכן רשאי לפעול.  
- מה מותר לו לשנות.  
- מתי הוא נדרש לבקש אישור.  
- כיצד תיעוד וניטור נשמרים לאורך זמן.  

הוא נחשב למסמך הבקרה העליון של סביבת הפיתוח  
ומבטיח איזון בין אוטונומיה מבוקרת לבין אחריות אנושית מלאה.  

---

## סיכום

קובץ זה הוא הליבה הארגונית של כל מתודולוגיית פיתוח מבוססת סוכנים.  
הוא גנרי לחלוטין, ניתן להרחבה,  
ומאפשר לכל צוות בעולם להגדיר בצורה ברורה את גבולות הסוכן  
כך שאוטומציה לעולם לא תעבור את הקו האנושי.  

שילוב סעיף **Version Control Integration**  
הופך אותו לשכבת הגנה אוניברסלית,  
המבטיחה שליטה אנושית, עקיבות מלאה, ותיעוד בלתי-ניתן למחיקה לכל שינוי.

---

© 2025 תומר קדם. חלק ממערך התבניות הרשמי של **Docs-as-System**.


</div>  

