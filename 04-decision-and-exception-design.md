# IT Support Automation – استخدام الذكاء الاصطناعي والقواعد والمراجعة البشرية

## 1. Where to Use AI? – أين نستخدم الذكاء الاصطناعي؟

- Analyze the employee's problem description.
- تحليل وصف المشكلة الذي يكتبه الموظف في الفورم.

- Generate a clear and concise problem summary.
- إنشاء ملخص واضح ومختصر للمشكلة.

- Classify the problem into a predefined category.
- تصنيف المشكلة ضمن فئة محددة مسبقًا، مثل `hardware`, `software`, `network`, or `email`.

- Assess the priority based on explicitly reported impact and predefined criteria.
- تحديد أولوية المشكلة بناءً على التأثير المذكور صراحةً ومعايير محددة مسبقًا.

- Identify ambiguous or insufficient information.
- اكتشاف المعلومات الغامضة أو غير الكافية.

## 2. Where to Use Rules? – أين نستخدم القواعد؟

- Validate required form fields.
- التحقق من تعبئة الحقول المطلوبة في الفورم.

- Validate the AI output against the predefined data schema.
- التحقق من أن مخرجات الذكاء الاصطناعي تطابق مخطط البيانات المحدد.

- Ensure `problem_type` and `priority` contain only allowed values.
- التأكد من أن `problem_type` و`priority` يحتويان على القيم المسموح بها فقط.

- Route tickets according to predefined priority and review rules.
- توجيه التذاكر بناءً على قواعد الأولوية والمراجعة المحددة مسبقًا.

- Send `critical` and `high` priority tickets to the appropriate support workflow.
- إرسال التذاكر ذات الأولوية `critical` و`high` إلى مسار الدعم المناسب.

- Route `needs_review` cases to human review.
- توجيه الحالات التي تحمل `needs_review` إلى المراجعة البشرية.

## 3. Where Is Human Intervention Needed? – أين نحتاج إلى تدخل بشري؟

- Review tickets when the problem description is unclear.
- مراجعة التذاكر عندما يكون وصف المشكلة غير واضح.

- Verify priority when the available information is insufficient.
- التحقق من الأولوية عندما تكون المعلومات المتاحة غير كافية.

- Handle conflicting or incomplete information.
- التعامل مع المعلومات المتعارضة أو غير المكتملة.

- Review security-related incidents according to company policy.
- مراجعة الحوادث المتعلقة بأمن المعلومات وفق سياسة الشركة.

- Approve exceptional decisions that cannot be handled safely by predefined rules.
- اعتماد القرارات الاستثنائية التي لا يمكن التعامل معها بأمان باستخدام القواعد المحددة مسبقًا.

## 4. What Are the Exceptions? – ما الحالات الاستثنائية؟

- Missing problem description.
- عدم وجود وصف للمشكلة.

- Unknown or ambiguous problem type.
- نوع المشكلة غير معروف أو غامض.

- Conflicting information in the employee's request.
- وجود معلومات متعارضة في طلب الموظف.

- Invalid JSON or missing output fields.
- مخرجات JSON غير صحيحة أو وجود حقول ناقصة.

- AI returns a value outside the allowed data schema.
- إرجاع الذكاء الاصطناعي قيمة غير موجودة ضمن مخطط البيانات المسموح به.

- Insufficient evidence to assign a reliable priority.
- عدم وجود أدلة كافية لتحديد الأولوية بشكل موثوق.

- AI service failure or timeout.
- فشل خدمة الذكاء الاصطناعي أو انتهاء مهلة الانتظار.

- Potential security incident requiring special handling.
- احتمال وجود حادث أمني يتطلب معالجة خاصة.

## 5. What Happens When an Exception Occurs? – ماذا يحدث عند ظهور حالة استثنائية؟

1. **Detect the Exception – اكتشاف الحالة**
   - The automation identifies missing information, invalid output, or a processing failure.
   - تكتشف الأتمتة المعلومات الناقصة أو المخرجات غير الصحيحة أو فشل المعالجة.

2. **Apply Validation Rules – تطبيق قواعد التحقق**
   - Validate the output and determine whether the request can continue automatically.
   - يتم التحقق من المخرجات وتحديد ما إذا كان يمكن متابعة الطلب تلقائيًا.

3. **Retry When Appropriate – إعادة المحاولة عند الحاجة**
   - Retry temporary AI service failures according to a predefined retry policy.
   - إعادة المحاولة عند حدوث أعطال مؤقتة في خدمة الذكاء الاصطناعي وفق سياسة محددة.

4. **Route for Human Review – التحويل إلى المراجعة البشرية**
   - Send unresolved or ambiguous cases to the IT support team.
   - تحويل الحالات التي لم تُحل أو التي تحتوي على غموض إلى فريق الدعم الفني.

5. **Preserve the Original Request – الاحتفاظ بالطلب الأصلي**
   - Keep the original employee submission for investigation and auditing.
   - الاحتفاظ بطلب الموظف الأصلي لأغراض المراجعة والتدقيق.

6. **Log the Exception – تسجيل الحالة الاستثنائية**
   - Record the exception type, timestamp, and processing status.
   - تسجيل نوع الحالة الاستثنائية ووقتها وحالة المعالجة.

7. **Resume Processing – استكمال المعالجة**
   - Continue the workflow after successful validation or human approval.
   - استكمال سير العمل بعد نجاح التحقق أو الحصول على موافقة بشرية.

## 6. Expected Outcome – النتيجة المتوقعة

- Routine tickets are processed automatically.
- تتم معالجة التذاكر الاعتيادية تلقائيًا.

- Invalid outputs are blocked from automatic routing.
- يتم منع المخرجات غير الصحيحة من الانتقال تلقائيًا إلى مسارات المعالجة.

- Ambiguous or high-risk cases receive human review.
- تخضع الحالات الغامضة أو عالية الخطورة للمراجعة البشرية.

- Failures are logged and handled according to predefined recovery rules.
- يتم تسجيل حالات الفشل والتعامل معها وفق قواعد استعادة محددة مسبقًا.

- No ticket is assigned an unsupported priority or fabricated classification.
- لا تُمنح أي تذكرة أولوية غير مدعومة بالمعلومات أو تصنيفًا مبنيًا على معلومات مختلقة.
