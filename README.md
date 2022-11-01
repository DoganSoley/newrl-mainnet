# NEWRL NODE MAİNNETE ÇEVİRME

Newrl Mainnet Kurulum

Öncelikle mainnet için testnette çalıştırdığınız cüzdanınız seçilmiş mi onu kontrol edin : https://cdn.discordapp.com/attachments/1022068099748466718/1036891927859175464/Newrl_Testnet_OG_Token_Wallets.pdf




Sıfırdan kurulum yapıyorsanız bu makaleden kurun : https://github.com/molla202/newrl-mainnet/blob/main/README.md daha sonra cüzdan değiştirme kısmını tekrar buraya gelip devam edin.

Daha önce testnet kurulumu yaptıysanız onu silmeden mainnete geçebilirsiniz fakat mainnet kurduğunuzda yeni bir cüzdan verecek onu eski testnette kullandığınız cüzdan ile değiştirmeniz gerekiyor sırasıyla gösteriyorum.

İlk önce sunucuyu açıp ;
```
cd newrl
```
```
screen -X -S newrl kill
```
```
scripts/install.sh mainnet
```
Yaptıktan sonra cüzdanı kontrol etmek için ;
```
python3 scripts/show_wallet.py
```
Yazıyoruz ve çıkan yere mainnet yazıp enter yapıyoruz daha sonra y diyoruz ve mainnet cüzdanını görüyoruz burda sizin eski kullandığınız cüzdan olmayacaktır bunu eskisiyle değiştirmeniz gerekiyor bunun için winscp programı kullanmanız gerekiyor.

winscp kurduktan sonra bu şekilde sunucumuzun ip kullanıcı adı ve şifre yazarak bağlanıyoruz

![1](https://user-images.githubusercontent.com/110679236/199261376-8bdea565-9145-44d9-b70f-cb73930a56ba.PNG)

Bağlandıktan sonra sırasıyla newrl dosyasına giriyoruz daha sonra data_mainnet dosyasına giriyoruz.

![2](https://user-images.githubusercontent.com/110679236/199261739-4c17c4d2-2de0-47b4-b4b1-85e55848f769.PNG)

auth.json dosyasını bulup açıyoruz.(eğer bu dosya sizde görünmüyorsa CTRL + ALT + H yaparak gizli klasörleri gösterin yeni kurulum yapıp cüzdan değiştirmek için girdiyseniz .auth.json dosyası hiç olmayabilir bu dosyayı kendiniz atın wallet.newrl.net sitesine giderek cüzdanı download edin wallet.json olarak indirir adını .auth olarak değiştirip data_mainnet dosyasının içine atın)

Açtığınızda mevcut cüzdanın public keyini görürsünüz onu eski testnette kullandığınız cüzdanın public keyi ile değiştirip kaydedip kapatıyoruz.

Daha sonra tekrar node içerisine dönüp mainnet için nodeyi çalıştıralım.
```
screen -S newrl
```
```
scripts/start.sh mainnet
```
Loglar akmaya başlayacak CTRL + A + D ile screenden çıkabilirsiniz.

Kurulum bu şekilde henüz OG tokenleri gönderilmedi gönderildiği zaman https://wallet.newrl.net/ üzerinden stake edip validatör olacağız şuanlık mainnet node kurulumu bu şekilde.
