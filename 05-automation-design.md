# Workflow Design

---

##  سير العمل من البداية إلى النهاية
### Step 1: Trigger – تشغيل الأتمتة


- يقوم الموظف بإرسال طلب دعم فني عبر الفورم.


**Output – المخرج:**
- استلام طلب دعم فني جديد.

### Step 2: Collect Inputs – جمع المدخلات


- استرجاع البيانات المدخلة في الفورم.

**Inputs – المدخلات:**
- `employee_name`
- `employee_email`
- `problem`

**Validation – التحقق:**

- التحقق من وجود الحقول المطلوبة.
- إذا كان وصف المشكلة مفقودًا، يتم تحويل الطلب للمراجعة.
### Step 3: AI Processing – معالجة البيانات بالذكاء الاصطناعي

- إرسال وصف المشكلة إلى AI by Zapier.
- استخراج المعلومات وتنظيمها باستخدام البرومبت المحدد مسبقًا.

**Structured Output – المخرجات المنظمة:**
- `problem_summary`
- `problem_type`
- `important of the problem`

### Step 4: Validate AI Output – التحقق من مخرجات الذكاء الاصطناعي

- التحقق من أن استجابة الذكاء الاصطناعي صحيحة.
- التأكد من وجود جميع الحقول المطلوبة.
- التأكد من أن نوع المشكلة والأهمية ضمن القيم المسموح بها.

**Decision – القرار:**

- إذا كانت المخرجات صحيحة ← الانتقال إلى المسار المناسب للمعالجة.
- إذا كانت المخرجات غير صحيحة ← التحويل للمراجعة البشرية.

### Step 5: Apply Routing Rules – تطبيق قواعد التوجيه

- استخدام قواعد محددة مسبقًا لتحديد الإجراء التالي.

**Routing Logic – منطق التوجيه:**

- اذا الطلب استوفى جميع الشروط المحددة تكون النتيجة كالاتي :
- problem_status : VALID
- routing: support team
  اذا لم يستوفي الشروط او كان همناك معلومات ناقصة تكون النتيجة كالاتي :
- problem_status : NEEDS_REVIEW
- routing:human_review 

### Step 6: Create or Update Ticket – إنشاء التذكرة أو تحديثها


### Step 7: Notify the Support Team – إشعار فريق الدعم

- إشعار فريق الدعم الفني بالطلبات الكاملة لاتخاذ الاجراء المناسب.
- إشعار فريق الدعم الفني بالطلبات التي تحتاج لمراجعة بشرية.

---

## 3. Final Workflow Diagram – المخطط النهائي

[Employee submits form]
        |
        v
[Trigger: New form response]
        |
        v
[Collect inputs]       
        |
        v
[AI by Zapier: Classify and summarize]
        |
        v
[Validate data]
        |
       
        v
[Apply routing rules]
        |
        valid output    +---- Invalid output ----> [Retry / Exception handling]
                             |
                             v
                          [Human review]
        |
        v
[Notify employee / Support team]


---

## 4. AI vs Rules vs Human – توزيع المسؤوليات

| Component – المكوّن | Responsibility – المسؤولية |
|---|---|
| AI by Zapier | Summarize and classify the reported issue – تلخيص المشكلة وتصنيفها |
| Validation Rules | Check output format and allowed values – التحقق من صيغة المخرجات والقيم المسموح بها |
| Routing Rules | Direct tickets to the correct queue – توجيه التذاكر إلى قائمة الدعم المناسبة |
| Human Review | Handle ambiguity, conflicts, and exceptional cases – معالجة الغموض والتعارضات والحالات الاستثنائية |
| Ticketing System | Store tickets and track their status – حفظ التذاكر وتتبع حالتها |
| Logging | Record failures and processing history – تسجيل الأخطاء وسجل المعالجة |

---

## 5. Implementation Checklist – قائمة التحقق قبل البناء

- [ ] Define the form fields – تحديد حقول الفورم.
- [ ] Finalize the AI prompt – اعتماد البرومبت النهائي.
- [ ] Define the data schema – تحديد مخطط البيانات.
- [ ] Define priority criteria with the IT team – اعتماد معايير الأولوية مع فريق الدعم.
- [ ] Configure validation and routing rules – إعداد قواعد التحقق والتوجيه.
- [ ] Define exception handling and retry limits – تحديد معالجة الاستثناءات وحدود إعادة المحاولة.
- [ ] Connect the ticketing system – ربط نظام التذاكر.
- [ ] Configure notifications – إعداد الإشعارات.
- [ ] Test normal, incomplete, invalid, and high-risk requests – اختبار الطلبات العادية والناقصة وغير الصحيحة وعالية الخطورة.
- [ ] Verify the end-to-end workflow before deployment – التحقق من سير العمل كاملًا قبل التشغيل الفعلي.

## 6. Expected Result – النتيجة المتوقعة

A reliable IT support automation that receives employee requests, structures the data, validates AI outputs, routes tickets according to predefined rules, and sends exceptional cases for human review.

نظام أتمتة موثوق للدعم الفني يستقبل طلبات الموظفين، وينظم البيانات، ويتحقق من مخرجات الذكاء الاصطناعي، ويوجّه التذاكر وفق قواعد محددة، ويحيل الحالات الاستثنائية إلى المراجعة البشرية.
