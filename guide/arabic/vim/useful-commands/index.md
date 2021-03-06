---
title: Useful Commands
localeTitle: أوامر مفيدة
---
# أوامر مفيدة

## وظائف أساسية

على الأرجح ستجد نفسك في وضع "عادي" ، فإنه يسمح لك بإدخال الأوامر عن طريق الضغط على النقطتين `:` مفتاح. للوصول إلى هنا من أوضاع أخرى ، يمكنك كتابة `ctrl + c` أو `escape` .

لتعديل النص والتنقل بطريقة مألوفة ، اضغط على `i` ، لوضع "insert". حاول التنقل باستخدام مفاتيح الأسهم في وضع "الإدراج" - راجع قسم "التنقل" أدناه للحصول على التفاصيل.

اعتمادا على التكوين ، يمكنك إدخال متصفح الملفات عن طريق كتابة الأمر وإدخاله `:e .` في الوضع "العادي". و "e" تعني التعديل ، وفترة الملف أو الدليل.

## التنقل

*   حركة المؤشر: يمكنك استخدام إما مفاتيح الأسهم أو `h` ، `j` ، `k` ، `l` (يسار ، إلى أسفل ، إلى أعلى ، يمين)
*   `gg` ينقلك إلى بداية الملف
*   `G` ينقلك إلى نهاية الملف
*   `:(num)` ينقلك إلى سطر معين في ملفك (ex-: 42 ينقلك إلى الخط 42)

## إنقاذ

1.  اضغط على `Escape` للتأكد من أنك في `normal mode` ؛
2.  اكتب في `:w` ("w" تعني "كتابة") ؛
3.  اضغط على `Enter` .

## الحفظ (إلى ملف جديد)

1.  اضغط على `Escape` للتأكد من أنك في `normal mode` .
2.  اكتب in `:w newfilename` (newfilename هو اسم ملف الملف الجديد الذي تريد حفظه).
3.  اضغط على `Enter` .

## الخروج Vi، Vim، Nvim، Gvim

1.  اضغط على الهروب لتحصل على وضع "عادي"
2.  `:q` سوف يرحل vim
3.  `:q!` سوف قوة إنهاء فيم
4.  `:qa` هذا سيغلق جميع الملفات المفتوحة
5.  `:qa!` يغلق جميع الملفات أثناء التخلي عن التغييرات
6.  `:q` يحفظ ويغلق الملف الحالي

(ملاحظة: الأمر `:q!` سوف يجبر Vim على الخروج دون حفظ. تأكد من الحفظ أولاً بكتابة الأمر `:w` إذا كنت لا تريد أن تفقد أي تغييرات قمت بها).

**أو**

*   اكتب ZZ (حفظ وإنهاء)
*   النوع `:wq` / `:x` (حفظ `:wq` ولكن باستخدام الأوامر "w" و "q" شائعة الاستخدام)

## قص ونسخ ولصق

*   `dd` يحذف (تخفيضات) سطر واحد
*   `yy` yanks (نسخ) سطر واحد
*   يمكنك استخدام `yy` و `dd` مسبوقًا برقم لقص أو نسخ أسطر متعددة (سيؤدي `13dd` سابقًا إلى قطع 13 سطرًا)
*   `p` لصق كل شيء من عازلة لصق

## لصق كتل من التعليمات البرمجية

في كثير من الأحيان ستجد نفسك تبحث عن حلول للمشاكل ، والعثور على شخص ما قد كتب كتلة من التعليمات البرمجية التي تفعل بالضبط ما تريد. إذا حاولت نسخ التعليمة البرمجية ولصقها مباشرةً في Vim ، فقد تجد أن الشفرة قد تم تنسيقها بشكل غريب أو لم يتم لصقها بشكل صحيح. يرجع ذلك إلى حقيقة أن فيم يقرأ كل حرف تقوم بلصقه بعد الآخر ، مما يعني أنه سيتم تنفيذ أي من مجموعات المفاتيح التي تقوم بتنشيط اختصار فيم ، وسوف يحاول فيم (وفشل) أن يقوم بادئة الكود الذي تم لصقه تلقائيًا.

للتغلب على هذا ، يمكنك استخدام **وضع لصق** Vim الذي يمكنك تنشيطه عن طريق إدخال الوضع العادي (اضغط على `escape` أو `crtl + c` ) واكتب `:set paste` ، ثم اضغط على ENTER. أنت الآن في وضع _اللصق_ . يمكنك بعد ذلك إدخال وضع الإدراج مع `i` ولصق كتلة النص / التعليمات البرمجية دون أي مشاكل! للعودة إلى Vim العادي دون وضع اللصق ، يمكنك الدخول إلى الوضع العادي ( `escape` or `crtl + c` ) ثم اكتب `:set nopaste` ، ثم اضغط على ENTER.

## ضبط أرقام الخطوط

1.  اضغط على الهروب لتحصل على وضع "عادي"
2.  النوع `:set number` ، اضغط على Enter

لتعيين أرقام الأسطر بشكل افتراضي:

1.  افتح / أنشئ ملف تهيئة `vim ~/.vimrc` باستخدام `vim ~/.vimrc`
2.  إضافة `set number` الخط ، اضغط على Enter

## فتح ملف داخل VIM

في VIM ، يمكنك فتح ملف داخل نفس النافذة عن طريق تعيين المؤشر على مسار وكتابة `gf` . سيخبر هذا VIM أن النص الحالي الذي يقع عليه المؤشر هو الملف الذي تريد فتحه. سيتم فتح الملف داخل محطة VIM حتى إذا كنت تريد العودة إلى النافذة السابقة ، فقط اكتب `ctrl+o` . سيخبر هذا VIM بالانتقال إلى الشاشة السابقة.

## كيفية تقسيم النوافذ

يمكنك تقسيم نوافذ vim وتحرير ملفين أو أكثر في نفس الوقت.

*   `:split` -> نافذة الانقسام (أفقي)
*   `:vsplit` -> نافذة الانقسام (عمودي)
*   `:vertical` جديد -> فتح ملف جديد في نافذة جديدة

للتنقل بين النوافذ ، يمكنك استخدام الأوامر التالية:

*   `CTRL-W h` - انتقل إلى النافذة على اليسار
*   `CTRL-W j` - انتقل إلى النافذة أدناه
*   `CTRL-W k` - انتقل إلى النافذة أعلاه
*   `CTRL-W l` - الانتقال إلى النافذة على اليمين
*   `CTRL-W t` - للانتقال إلى النافذة العلوية
*   `CTRL-W b` - الانتقال إلى النافذة السفلية

## التراجع عن إعادته

يجب تنفيذ هذه الإجراءات في **الوضع العادي** .

**التراجع** : اضغط على `u` أو اكتب `:undo` واضغط على `Enter` .

**الإعادة** : اضغط على `U` ( `Shift` + `u` ) أو اكتب `:redo` واضغط على `Enter` .

## فتح ملف في سطر معين

*   vi filename + n، where n is the line number

## فتح ملف يبحث عن كلمة / مصطلح

*   vi filename + / word، where word is what you are looking for. سيتم وضع المؤشر على أول ظهور للكلمة.

## البحث عن ملف في فيم

عندما تكون في الوضع العادي (اضغط على مفتاح `escape` للتأكد) ، يمكنك البحث عن أي مصطلح في الوثيقة بكتابة `/` ، متبوعًا بالمصطلح الذي تبحث عنه ، ثم الضغط على `enter` . على سبيل المثال ، اكتب `/hello` واضغط على `enter` للبحث عن الكلمة "hello" في الملف الحالي.

يمكنك التخطي إلى التكرار التالي لمصطلح البحث الخاص بك عن طريق الضغط على `n` ، أو التكرار السابق بالضغط على `N` `*` يبحث عن الكلمة تحت المؤشر.

إذا كنت ترغب في تمييز جميع أنواع مطابقة البحث `:set hlsearch` أو استخدم الأمر المختصر `:set hls` . الاستخدام `:set noh` لإيقاف تشغيل التمييز حتى البحث التالي.

## تجميع المشروع

همة لديها التكامل ضيق جدا مع `make` أداة بناء الأتمتة. إذا كان مشروعك يستخدم Makefile ، فيمكنك كتابة `:make` at Vim command line لتشغيل أداة `make` الخاصة بالنظام الخاص بك. وفيم طباعة إخراج `make` على الشاشة وتجلب لك إلى الخطأ الأول، إن وجدت، عندما `make` يكمل الأوامر. يمكنك بعد ذلك الانتقال من خلال أخطاء التحويل البرمجي والتحذيرات في رمز المشروع باستخدام الأمرين `:cn` و `:cp` ، بالنسبة إلى `:cp` التاليين والسابقين على التوالي.

## ابحث واستبدل

1.  اضغط على `Escape` للتأكد من `normal mode` في `normal mode` ؛
2.  اكتب `:` (ستنتقل إلى `command mode` ) ؛
3.  اكتب `%s,word_to_be_replaced,new_word,g` ؛
4.  اضغط على `ENTER` .

هام: إذا كنت تريد استبدال التكرار الأول للكلمة ، فأزل `g` في النهاية.

## أريد أن أتعلم فيم!

للمبتدئين ، تأتي فيم مع برنامج تعليمي مدمج! يمكنك الوصول إليه عن طريق تشغيل `vimtutor` من المحطة الطرفية الخاصة بك وهذا سيطلق برنامج تعليمي تفاعلي حول _كيفية البدء مع Vim_ (يستغرق حوالي 15 دقيقة للعمل من خلاله).

إذا لم تكن واثقاً من اللغة الإنجليزية ، فيمكنك أن `vimtutor` لك `vimtutor` لغتك المفضلة. على سبيل المثال سوف `vimtutor fr` بدء البرنامج التعليمي باللغة الفرنسية!

## أوامر أخرى مفيدة

*   `gg=G` يحدد المسافة البادئة للملف بأكمله
*   إذا كنت تريد معرفة المزيد عن أمر معين ، اكتب `:help` متبوعًا باسم الأمر (ex-: help: w)

اقرأ بقية دليل Vim الخاص بنا للحصول على فهم أفضل لهذا المحرر القوي.

## موارد آخرى

*   [Vim Golf](https://vimgolf.com/) - طريقة جيدة للتعلم من القيام بتحديات vim للحصول على أقل كمية من ضغطات المفاتيح. يمكنك رؤية الحلول المقدمة من قبل الآخرين إذا لم تتمكن من تحديد التحدي.
*   [Vim Adventures](https://vim-adventures.com/) - طريقة مرحة ومسلية لتعلم Vim حيث يمكنك تحديد المسارات الرئيسية المختلفة مع كل مستوى جديد في اللعبة.
*   [Open Vim](http://www.openvim.com/) - برنامج تعليمي تعليمي تفاعلي يقوم بتعليم الأوامر الأساسية