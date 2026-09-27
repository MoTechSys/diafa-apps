# تطبيقات الضيافة — أندرويد فقط

> 🗺️ **هذا واحد من 3 مستودعات.** اقرأ [`ECOSYSTEM.md`](ECOSYSTEM.md) أولًا:
> - [keif_blins](https://github.com/MoTechSys/keif_blins) — الكود المصدري
> - **diafa-apps** (هنا) — ملفات APK (الإصدارات) + القفل عن بُعد
> - [diafa-signing-keys](https://github.com/MoTechSys/diafa-signing-keys) (خاص) — مفتاح التوقيع

## التحميل المباشر (آخر إصدار)
| | أغلب الجوالات | الجوالات القديمة |
|---|---|---|
| **كيف الضيافة** | [arm64](https://github.com/MoTechSys/diafa-apps/releases/download/v2.4.0/keif-aldiafa-v2.4.0-arm64.apk) | [armv7](https://github.com/MoTechSys/diafa-apps/releases/download/v2.4.0/keif-aldiafa-v2.4.0-armv7.apk) |
| **أصول الضيافة** | [arm64](https://github.com/MoTechSys/diafa-apps/releases/download/v2.4.0/asoul-aldiafa-v2.4.0-arm64.apk) | [armv7](https://github.com/MoTechSys/diafa-apps/releases/download/v2.4.0/asoul-aldiafa-v2.4.0-armv7.apk) |

| التطبيق | اسم الحزمة (ثابت — لا يتغير أبدًا) | المجلد |
|---|---|---|
| كيف الضيافة | `com.hospitalitybilling.keif_diafa` | [`كيف الضيافة/`](كيف%20الضيافة) |
| أصول الضيافة | `com.hospitalitybilling.osool_diafa` | [`أصول الضيافة/`](أصول%20الضيافة) |

- **التنزيل:** من صفحة [الإصدارات](../../releases/latest) — لكل تطبيق ملفان: `arm64` (أغلب الجوالات الحديثة) و`armv7` (الجوالات القديمة فقط).
- **التحديث:** ثبّت الملف الجديد فوق القديم مباشرة — **لا تحذف القديم**؛ البيانات تبقى.
- التطبيقان منفصلان تمامًا (يمكن تثبيتهما معًا على نفس الجوال، ولكلٍّ بياناته).

## القفل عن بُعد
داخل مجلد كل تطبيق ملف `license.json`:

```json
{ "active": true, "code": "XXXX", "message": "الرسالة التي تظهر للمستخدم" }
```

| التعديل | النتيجة في التطبيق |
|---|---|
| `"active": false` | يُقفل ويطلب الكود (تظهر الرسالة) |
| `"active": true` | يفتح فورًا |
| تغيير `code` | يُقفل من فعّل بالكود القديم |
| حذف الملف | قفل نهائي — لا يُقبل أي كود |

- يُفحص عند فتح التطبيق وعند الرجوع إليه (كل 10 دقائق كحد أدنى).
- بلا إنترنت: آخر حالة معروفة. البيانات لا تُمس أبدًا.
- قفل أحد التطبيقين لا يؤثر على الآخر.

> ⚠️ هذا المستودع يجب أن يبقى **عامًا** — التطبيق يقرأ الملف بلا تسجيل دخول.
> لا تغيّر أسماء المجلدات ولا اسم المستودع.
