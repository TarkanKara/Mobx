### [Directory Structure](https://github.com/TarkanKara/Mobx/tree/master/lib)
```
📂lib
 │───main.dart  
 │───📂mobx_1_counter 
 |   │──counter.dart
 |   │──counter.g.dart
 |

```
# [Mobx](https://mobx.netlify.app/getting-started/)
* **Mobx** oluşturmak istediğiniz uygulamalar üzerinde, uygulamanızın **reaktif verilerini** UI (veya herhangi bir gözlemci) ile yönetimi kolaylaştıran bir state yönetim kütüphanesidir.
* **Mobx,** kullanıcı arayüzünü iş (logic) mantığından ayırmayı kolaylaştırarak kodlama sürecini; hızlı, test edilebilir ve yeniden kullanabilir hale getirir.

### Install Dependencies
- pubspec.yaml dosyasına **dependencies** altına aşağıdaki paketleri yükleyiniz.
    * **[mobx 2.1.3](https://pub.dev/packages/mobx)**
    * **[flutter_mobx 2.0.6+5](https://pub.dev/packages/flutter_mobx)**

- pubspec.yaml dosyasına **dev_dependencies** altına aşağıdaki paketleri yükleyiniz.
    * **[build_runner 2.3.2](https://pub.dev/packages/build_runner)**
    * **[mobx_codegen 2.1.1 ](https://pub.dev/packages/mobx_codegen)**

### Installe Extensions
* Vs code **[flutter_mobx](https://marketplace.visualstudio.com/items?itemName=Flutterando.flutter-mobx)** eklentisini ekliyoruz.

## Add a Store
- Mobx ile birlikte öncelikle bir **store** oluşturmamız gerekiyor.
- MobX'te store, ilgili **observable state** i tek bir sınıf altında toplamaya olayı
- counter.dart adında bir dosya oluşturup, kurduğumuz eklenti sayesinde aşağıdaki kodları yazıyoruz.

```dart
class Counter = _CounterBase with _$Counter;

abstract class _CounterBase with Store {
  
}
```
- Şimdi **counter.g.dart** dosyasını oluşturalım
- Vs code terminal ekranına **flutter pub run build_runner build** yazmamız yeterli olacaktır.
- **abstract class** içerisine yazdığımız kodları **.g.dart** dosyalarını otomatik olarak oluşturmak istiyorsanız, aşağıdaki komutu kullanabilirsiniz:
    * **flutter pub run build_runner watch**, bunu yapmak istemiyorsan Vs code **[flutter_mobx](https://marketplace.visualstudio.com/items?itemName=Flutterando.flutter-mobx)** eklentisi bizler için **.g.dart** dosyasnın içeriğini dolduracaktır.

:bangbang::bangbang:

* **Reaktif** veri terimi, verilerdeki bir değişikliğin ilgili her gözlemciye bir bildirim gönderilmesine neden olduğu anlamına gelir.

## Mobx Core Concepts
### **@observable**
- Gözlenebilirler, uygulamanızın reaktif durumunu temsil eder.
- Değişkenler yaratmamıza olanak veriyor.
- **@observable** degisken_ismi = degisken_degeri;
- Değişken oluşturmanın farklı yoları var 

```dart
final counter = Observable(0);
// counter adında bir değişken ve değeri sıfır

@observable
final counter = 0;
//counter adında bir değişken ve değeri sıfır

```


