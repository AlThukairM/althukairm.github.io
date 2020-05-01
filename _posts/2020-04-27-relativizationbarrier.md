---
title: "النسبية وعلوم الحاسب"
layout: post
---

أول مرة أتذوق جمال الرياضيات كان عند قراءتي لنظرية غودل الشهيرة (Gödel's Incompleteness Theorem) والتي تقتضي عدم وجود نظام إثبات يستطيع إثبات جميع النظريات الرياضية. ولست هنا لأتكلم عن هذه النظرية [^1].. ولكني هنا لأشارككم theme في الرياضيات يثير إعجابي دائمًا، وهو إثبات استحالة أمرٍ ما.

لب إثبات نظرية غودل هو التعبير عن العبارة: "هذه العبارة لا يمكن إثباتها" كنظرية رياضية. وهذه الطريقة شبيهة بإثباتٍ لكانتور (Cantor's uncountability theorem)[^2] الذي أثبت عدم قابلية الأعداد الحقيقية (0.5، 0.33...، ط) للعد، أو بتعبير آخر أن "عدد" الأعداد الحقيقية أكبر من "عدد" الأعداد الصحيحة. أولا، لنلاحظ أن كلتا النظريتين تحاولان إثبات أن مجموعة ما أكبر من أخرى: فنظرية غودل تقول أن مجموعة النظريات الرياضية أكبر من مجموعة النظريات التي يمكن إثباتها (بمعنى: يوجد نظرية لا يمكن إثباتها) ونظرية كانتور تقول أن مجموعة الأعداد الحقيقية أكبر من مجموعة الأعداد الصحيحة. والملاحظة الأخرى هي أن طريقة إثبات كلتا النظريتين يقوم على استغلال خاصية معينة للمجموعة الصغرى ومحاولة إيجاد/بناء شيء يخالف هذه الخاصية، ففي نظرية غودل هذه الخاصية هي "إمكانية الإثبات" وفي الأخرى "إمكانية سرد الأعداد".. 

وقد اشتهرت هذه الطريقة في الإثبات والتي تسمى بـ diagonalization method[^4]. حتى أن تورنغ استعملها في نظريته الشهيرة (undecidability theorem)[^2] التي تقول بوجود "مشاكل" لا يمكن لأي كمبيوتر حلها. ويمكن النظر لهذه الطريقة على أنها تبدأ بافتراض قدرة محاكاة وتوقع خاصية/ناتج شيء معين (ففي نظرية غودل افترضنا أننا نمتلك القدرة على الحكم على عبارةٍ ما بأنها قابلة للإثبات أو لا، وفي نظرية تورنغ نفترض قدرتنا على معرفة ما إذا كان برنامجٌ ما يستطيع حل مشكلةٍ ما عند معطًى ما).. ثم استخدام هذه القدرة على المحاكاة لبناء شيء يخالف جميع التوقعات ومن ثم التوصل إلى تناقض. والنظر إلى الـdiagonalization method بهذه الطريقة، هو ما مكّن باحثي النتيجة التالية من توصل إلى نتيجتهم.

**بعد هذه المقدمة الطويلة، نأتي إلى لب موضوعنا:** إن كانت النظريات السابقة أثارت اهتمامي لإثباتها استحالة حدوث أمرٍ ما، فالنظرية التالية أحق بالإهتمام.. كيف لا وهي قد أثبتت استحالة [^5] استخدام هذه الطريقة، التي طالما استُخدمت لإثبات استحالة الكثير من الأمور، لحل المشكلة المشهورة P vs. NP (!)

[سؤال P vs. NP من أكثر الأسئلة الرياضية شهرةً](https://althukairm.github.io/2019/12/07/complexity.html){:target="_blank"}، وقد يبدو سؤالا مثاليا لاستخدام الطريقة سابقة الذكر لأننا نريد أن نثبت أن المجموعة NP أكبر من المجموعة P.. 

ولكن BGS[^3] استطاعوا أن يعبروا عن طريقة الإثبات diagonialization تعبيرًا رياضيا، وذلك [بابتكار نموذجً حسابي (model of computation)](https://althukairm.github.io/2019/12/07/complexity.html){:target="_blank"} أُعرِبه بـ "آلة تورنغ عالمة الغيب" (Oracle Turing Machine) والذي يعمم طريقة الإثبات هذه (كما تعمم آلة تورنغ مثلا حواسيب اليوم) ثم استخدام هذا النموذج في تقصي افتراض أن P = NP وافتراض أن P != NP وفي كلا الافتراضين يتوصلون إلى تناقض.. وبما أن أحد هذين الافتراضين يجب أن يكون صحيحا، يتضح أن هذه الطريقة (diagonlization) لن توصل إلى نتيجة.

سميت هذه النتيجة بـ the relativization barrier لكونها حاجزًا يمنع الوصول إلى إثبات إلى P vs. NP ويشرح أحد أوجه صعوبة هذا السؤال.. وأما سبب تسميته بـrelativization وهو سر عنوان هذه التدوينة فيرجع إلى كون آلة تورنغ عالمة الغيب لا تعلم كل الغيب بالضرورة وإنما بعضه، و**نسبةً** إلى هذا الغيب الذي تعلمه يختلف كون P = NP أو P != NP.. 

أتى بعد الـrelativization barrier حاجزين أخريين: هما الـnatural proofs وalgebrization ولعلي أكتب عنهما لاحقًا بإذن الله.. وأفصل في هذه النتيجة أكثر لأن جمالها له أبعاد وهذه التدوينة تكاد لم تلمس قشر بُعد واحد من أبعادها.. لكن عزاءنا أن هذه التدوينة مقدمة فقط. وكل عام وأنتم بخير!

# مصادر

هذه التدوينة مستلهمة (وإن صح التعبير مترجمة بتصرف) من كتاب [Mathematics and Computation](https://www.math.ias.edu/avi/book) بالتحديد الفصل 5.1 من نسخة أغسطس 2019.

[^1]: صدقوني لقد حاولت، لكني لا أملك العلم الكافي ولا اللغة السهلة التي تؤهلني لهذه المهمة. ولكن يوجد كتاب رائع في هذا الصدد Gödel, Escher, Bach by Douglas Hofstadter وهو أكثر من مجرد شرح لنظرية غودل.
[^2]: كتاب رائع أرشحه يشرح نظرتا كانتور وتورنغ هو The Annotated Turing by Charles Petzold
[^3]: T. Baker, J. Gill, and R. Solovay. Relativizations of the P =? NP question. _SIAM Journal on Computing_, 4:431–442, 1975.
[^4]: نتيجة أخرى تُوصل لها بهذه الطريقة هي الـ[Time-hierarchy theorem](https://en.wikipedia.org/wiki/Time_hierarchy_theorem){:target="_blank"}.
[^5]: استحالة أن نجد إثبات يعتمد على الـdiagonializatino **فقط**، لكن هذه النتيجة لا تستبعد وجود طريقة تدمج هذا التكنيك مع آخر لإيجاد طريقة إثبات تتعدى هذا الحاجز.