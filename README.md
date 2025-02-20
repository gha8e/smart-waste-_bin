
# شرح الكود

استيراد المكتبات:

os: للتعامل مع الملفات والمجلدات.

cvzone: مكتبة مساعدة في معالجة الصور والتصنيف.

cv2: مكتبة OpenCV لالتقاط الصور من الكاميرا ومعالجتها.

Classifier من cvzone.ClassificationModule: لتحميل النموذج المدرب وتنفيذ التصنيف.

إعداد الكاميرا وتحميل نموذج التصنيف:

cap = cv2.VideoCapture(0): فتح الكاميرا.

classifier = Classifier('Resources/Model/keras_model.h5', 'Resources/Model/labels.txt'): تحميل النموذج المدرب وقائمة التصنيفات.

تحميل الصور المطلوبة للعرض:

imgArrow = cv2.imread('Resources/arrow.png', cv2.IMREAD_UNCHANGED'): تحميل صورة السهم.

تحميل صور النفايات المختلفة من المجلد Resources/Waste.

تحميل صور الحاويات المناسبة من المجلد Resources/Bins.

إنشاء قاموس لتحديد نوع الحاوية بناءً على تصنيف النفايات:

يقوم القاموس classDic بربط فئات النفايات بأرقام الحاويات المناسبة.

بدء الحلقة الرئيسية لمعالجة الفيديو وتصنيف النفايات:

يتم التقاط صورة من الكاميرا ومعالجتها باستخدام classifier.getPrediction(img).

إذا تم تصنيف صورة النفايات، يتم عرض صورة النفايات مع السهم الذي يشير إلى الحاوية المناسبة.

يتم دمج الصور باستخدام cvzone.overlayPNG().

يتم عرض النتيجة النهائية في النافذة cv2.imshow("Output", imgBackground).
# المخرجات 
<img src="https://github.com/user-attachments/assets/579a0738-adbe-4041-b49e-d99cb3918ae5" width=300 >

