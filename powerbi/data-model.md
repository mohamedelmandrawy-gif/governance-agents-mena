# Power BI Data Model / نموذج بيانات Power BI

Four CSV tables, linked by `company_code`. / أربعة جداول CSV مرتبطة بحقل `company_code`.

| Table / الجدول | Purpose / الغرض | Key columns / الأعمدة الرئيسية |
|---|---|---|
| `companies.csv` | Company dimension / بيانات الشركات | company_code, sector, legal_form, country, employees_band |
| `diagnostic_scores.csv` | Maturity scores per question / درجات النضج لكل سؤال | company_code, assessment_date, question_id, domain, score |
| `obligations.csv` | Legal & regulatory obligations / الالتزامات القانونية والتنظيمية | company_code, obligation_id, description_en, description_ar, legal_reference, owner_seat, due_date, status |
| `kpis.csv` | Governance & business KPIs / مؤشرات الحوكمة والأعمال | company_code, period, kpi_name, owner_seat, target, actual |

## Relationships / العلاقات
`companies[company_code]` 1 → * `diagnostic_scores`, `obligations`, `kpis`

## Suggested measures (DAX) / مقاييس مقترحة
```
Avg Maturity = AVERAGE(diagnostic_scores[score])
High Gaps = COUNTROWS(FILTER(diagnostic_scores, diagnostic_scores[score] <= 2))
Overdue Obligations = COUNTROWS(FILTER(obligations, obligations[status] <> "Done" && obligations[due_date] < TODAY()))
KPI Achievement % = DIVIDE(SUM(kpis[actual]), SUM(kpis[target]))
```

## Suggested pages / الصفحات المقترحة
1. Board overview: maturity heatmap by domain / نظرة عامة للمجلس: خريطة النضج حسب المجال
2. Compliance calendar: obligations by due date and status / تقويم الالتزام حسب التاريخ والحالة
3. KPI tracker by executive seat / متابعة المؤشرات حسب كل مقعد تنفيذي

All sample data in `sample-data/` is fictional. / كل البيانات في مجلد العينات افتراضية.
