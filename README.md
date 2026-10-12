# IT Support Automation

## 1. Problem – المشكلة
Employees submit IT support requests through forms, making it difficult to organize, classify, and prioritize issues manually.

يقوم الموظفون بإرسال طلبات الدعم الفني عبر الفورم، مما يجعل تنظيم المشاكل وتصنيفها وتحديد أولوياتها يدويًا أمرًا صعبًا.

## 2. Solution – الحل
An AI-powered automation that summarizes employee issues, classifies problem types, assigns priorities, and routes requests for support or human review.

أتمتة تعتمد على الذكاء الاصطناعي لتلخيص مشاكل الموظفين، وتصنيف أنواعها، وتحديد أولوياتها، وتوجيه الطلبات إلى الدعم الفني أو المراجعة البشرية.

## 3. How It Works – آلية العمل
1. Employee submits a support form – يرسل الموظف طلب الدعم.
2. Automation collects the form data – تجمع الأتمتة بيانات الفورم.
3. AI summarizes and classifies the problem – يلخص الذكاء الاصطناعي المشكلة ويصنفها.
4. Validation rules check the output – تتحقق القواعد من صحة المخرجات.
5. Routing rules direct the ticket to the appropriate queue – توجّه القواعد التذكرة إلى المسار المناسب.
6. Exceptional cases are sent for human review – تُحوّل الحالات الاستثنائية إلى المراجعة البشرية.

## 4. Tools Used – الأدوات المستخدمة
- **Forms:** Collect employee support requests – استقبال طلبات الموظفين.
- **Zapier:** Automate the workflow – أتمتة سير العمل.
- **AI by Zapier:** Summarize and classify problems – تلخيص المشاكل وتصنيفها.
- **Ticketing System / Database:** Store and track requests – حفظ الطلبات وتتبعها.
- **Email / Notifications:** Notify the support team – إشعار فريق الدعم.

## 5. How to Test – كيفية الاختبار
Test the automation using the following scenarios:

| Test Case – حالة الاختبار | Expected Result – النتيجة المتوقعة |
|---|---|
| Clear problem description – وصف واضح | Correct summary and classification – ملخص وتصنيف صحيحان |
| Missing problem description – وصف مفقود | Request review or additional information – طلب المراجعة أو معلومات إضافية |
| High-impact issue – مشكلة ذات تأثير كبير | Priority assigned according to defined rules – تحديد الأولوية وفق القواعد |
| Ambiguous request – طلب غامض | Human review required – الحاجة إلى مراجعة بشرية |
| Invalid AI output – مخرجات غير صحيحة | Validation failure and exception handling – فشل التحقق ومعالجة الاستثناء |
| AI service failure – فشل خدمة الذكاء الاصطناعي | Retry or error handling – إعادة المحاولة أو معالجة الخطأ |

**Success Criteria – معايير النجاح**
- Accurate problem summaries and classifications – دقة تلخيص المشاكل وتصنيفها.
- Valid structured outputs – مخرجات منظمة وصحيحة.
- Correct ticket routing – توجيه صحيح للتذاكر.
- No silent loss of failed requests – عدم فقدان الطلبات الفاشلة دون تنبيه.
