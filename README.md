# Governance Agents MENA

**An open-source, bilingual (English/Arabic) agent-based corporate governance framework for companies in Egypt and the GCC, with Power BI reporting.**

> Status: early stage / work in progress. Contributions and feedback are welcome.

---

## English

### Why this project
Most family businesses and SMEs in Egypt and the GCC have no affordable, structured governance tooling, and almost none of it exists in Arabic. This project provides an open framework that consultants, lawyers, boards and management teams can reuse and improve.

### What it does
1. **Virtual advisory board** – seven specialised AI agents (CEO, CFO, CHRO, COO, CIO/CTO, CLO, CCO). Each reviews a company case from its own perspective; a chair step combines the opinions into one integrated recommendation.
2. **Governance diagnostic** – a scored maturity checklist (1–5) across governance, control environment, compliance and organisation, producing a prioritised gap list.
3. **Compliance and obligations register** – a structured register of legal and regulatory obligations with owners and due dates.
4. **Power BI reporting** – a simple data model (CSV tables) that feeds governance KPIs, maturity scores and regulatory deadlines into Power BI dashboards for boards.

### Repository structure
```
agents/          Agent definitions (one file per executive seat) + template
templates/       Case brief, governance diagnostic checklist, obligations register
powerbi/         Data model description + sample (fictional) CSV data
docs/            Roadmap and methodology notes
```

### How to use
1. Fill in `templates/case-brief-template.md` for a company (use anonymised data).
2. Run each agent in `agents/` against the case brief with Claude (or any capable LLM).
3. Score the company with `templates/governance-diagnostic-checklist.md`.
4. Export scores and obligations to the CSV tables in `powerbi/sample-data/` and load them into Power BI.

### Legal frameworks referenced
Egyptian Companies Law 159/1981, Investment Law 72/2017, Labour Law 14/2025, Personal Data Protection Law 151/2020, FRA corporate governance rules; KSA and UAE companies and labour laws. Outputs are advisory and must be reviewed by a qualified professional.

### License
MIT – see `LICENSE`.

### Author
Mohamed Elmandarawy – corporate lawyer and Legal & Compliance Director, Cairo.

---

## العربية

### لماذا هذا المشروع
معظم الشركات العائلية والصغيرة والمتوسطة في مصر ودول الخليج لا تملك أدوات حوكمة منظمة وبتكلفة مناسبة، ويكاد لا يوجد منها شيء باللغة العربية. يقدم هذا المشروع إطارًا مفتوح المصدر يمكن للمستشارين والمحامين ومجالس الإدارة والإدارات التنفيذية استخدامه وتطويره.

### ماذا يقدم
١. **مجلس استشاري افتراضي** – سبعة وكلاء ذكاء اصطناعي متخصصين (الرئيس التنفيذي، المدير المالي، مدير الموارد البشرية، مدير العمليات، مدير التقنية، المدير القانوني، مدير الالتزام). يراجع كل وكيل حالة الشركة من منظوره، ثم تُدمج الآراء في توصية واحدة متكاملة.
٢. **تشخيص الحوكمة** – قائمة تقييم نضج بدرجات من ١ إلى ٥ تغطي الحوكمة وبيئة الرقابة والالتزام والتنظيم، وتنتج قائمة فجوات مرتبة حسب الأولوية.
٣. **سجل الالتزامات القانونية والتنظيمية** – سجل منظم للالتزامات مع المسؤول عن كل التزام وتاريخ استحقاقه.
٤. **تقارير Power BI** – نموذج بيانات بسيط (جداول CSV) يغذي لوحات Power BI بمؤشرات الحوكمة ودرجات النضج والمواعيد التنظيمية لمجالس الإدارة.

### طريقة الاستخدام
١. املأ نموذج ملخص الحالة `templates/case-brief-template.md` ببيانات مُجهّلة.
٢. شغّل كل وكيل من مجلد `agents/` على ملخص الحالة.
٣. قيّم الشركة باستخدام قائمة تشخيص الحوكمة.
٤. انقل الدرجات والالتزامات إلى جداول CSV في `powerbi/sample-data/` وحمّلها في Power BI.

### تنبيه
المخرجات استشارية ويجب مراجعتها من مختص مؤهل. لا تُرفع أي بيانات عملاء حقيقية إلى هذا المستودع.

### الترخيص
MIT – راجع ملف `LICENSE`.
