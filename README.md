# IT Support Automation

## 1. Problem – المشكلة

يقوم الموظفون بإرسال طلبات الدعم الفني عبر الفورم، مما يجعل تنظيم المشاكل وتصنيفها وتحديد أهميتها يدويًا أمرًا صعبًا.

## 2. Solution – الحل
أتمتة تعتمد على الذكاء الاصطناعي لتلخيص مشاكل الموظفين، وتصنيف أنواعها، وتحديد أهميتها، وتوجيه الطلبات إلى الدعم الفني أو المراجعة البشرية.

## 3. How It Works – آلية العمل
1. Employee submits a support form – يرسل الموظف طلب الدعم.
2. Automation collects the form data – تجمع الأتمتة بيانات الفورم.
3. AI summarizes and classifies the problem – يلخص الذكاء الاصطناعي المشكلة ويصنفها.
4. Validation rules check the output – تتحقق القواعد من صحة المخرجات.
5. Routing rules direct the ticket to the appropriate queue – توجّه القواعد التذكرة إلى المسار المناسب.
6. Updating request data in the Google Sheet - تحديث بيانات الطلب في نفس السجل
7. Exceptional cases are sent for human review – تُحوّل الحالات الاستثنائية إلى المراجعة البشرية.

## 4. Tools Used – الأدوات المستخدمة
- **Forms:** Collect employee support requests – استقبال طلبات الموظفين.
- **Zapier:** Automate the workflow – أتمتة سير العمل.
- **AI by Zapier:** Summarize and classify problems – تلخيص المشاكل وتصنيفها.
- **Google sheets:** تسجيل وتحديث بيانات الطلب.
- **Email / Notifications:** Notify the support team – إشعار فريق الدعم.

## 5. How to Test – كيفية الاختبار
Test the automation using the following scenarios:

| Test Case – حالة الاختبار | Expected Result – النتيجة المتوقعة |
|---|---|
| Clear problem description – وصف واضح |  ملخص وتصنيف صحيحان |
| Missing problem type – نوع المشكلة | مراجعة بشرية مفقود |
| A problem where details regarding its impotrant are missing. – مشكلة مفقود فيها تفاصيل حول اهمينها |  مراجعة بشرية |


**Success Criteria – معايير النجاح**
-  دقة تلخيص المشاكل وتصنيفها.
-  مخرجات منظمة وصحيحة.
- توجيه صحيح للطلبات.
-  عدم فقدان الطلبات الفاشلة دون تنبيه.
