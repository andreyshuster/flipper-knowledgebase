
# Mifare Classic 1-4K
The best way to familarise yourself and understand Mifare classic is to read the datasheets as those provide a full structural breakdown 

[Link to datasheets](https://github.com/equipter/flipper-knowledgebase/tree/main/NFC/Mifare%20Classic/Datasheets-Specs)

## What is it?
Mifare Classic "MFC" is a type of High Frequency (13.56mhz) rfid chip commonly used for access control in Hotels, Schools, offices, large institutions, apartments and much more. MFC is a very common chip to find out in the wild. 

Mifare classic comes in multiple form factors most notably:
- CR80 standard credit card size
- Teardrop Fob
- Circular and rectangular Stickers
size and shape of an antenna can alter its effective read/write range 

Mifare Classics also come in 3 different storage sizes:
- Mifare Classic 1K - 1KB of storage with 720 usables bytes 
- Mifare Classic 2K - 2KB of storage with 1440 usable bytes ~ effectively doubles the 1k variant with no noticeable data structure change 
- Mifare Classic 4K - 4Kb of storage with 3360 usable bytes ~ has a slightly different data structure in the second half of the tags storage where sectors contain 15 blocks +1 sector trailer block as opposed to 1k/2k and the first half of the 4k which has 3 blocks +1 sector trailer. 

**see data strucuture diagram at bottom of page**

Mifare classic is a woefully vulnerable technology that has multiple exploitations available to the average person making it relatively easy to create copies of, the large amount of vulnerabilities somehow do not affect its great popularity and wide distribution, the majority of access control system suppliers still offer mifare classic as an option and there is no end in sight for this. win win situation.

---

## FAQs
### Does cracking the keys damage the card?
Nope not at all, all its doing is reading/attemping to read the sectors, no damage to be caused

### Can Flipper Emulate Mifare Classics?
Currently, as of 25/04/2022 no. The hardware does support it for when it is implemented though.

### Can flipper Write to mifare classics 
Currently, as of 25/04/2022 no. The hardware does support it for when it is implemented though.

### My flipper doesnt find any keys / only finds some keys when running "read mifare classic"
This is because the flipper uses a dictionary composed of about 1300 Keys to check against the card/fob to see if it can find any matches, if your Mifare classic has keys that are not in this dictionary it will not be able to discover them. 

### I want to clone this Mifare classic NOW! how do i do that?
With the current lack of support for writing/cracking keys, currently the flipper is not a feesible option for cloning mifare classics. If you are looking to make copies of a mifare classic you will need additional hardware such as a proxmark3 easy, for more information ping/message Equip#1515 in the discord 

---



## Photos
Mifare Classic CR80 form factor

![Mifare Classic antenna inside CR80](https://user-images.githubusercontent.com/72751518/165157883-f107d27c-058f-445d-8744-ad2d9c3fcd62.png)

(credit: Doegoxx rfidpics git repo)

---

Mifare Classic 1k (WUID) Teardrop fob form factor

![Mfc fob](https://cdn.discordapp.com/attachments/954422698879098990/966759997486813304/IMG_4014.jpg)

(Credit: Equip#1515 Discord)

---

Mifare Classic Circular sticker

![Sticker](https://www.idcardsdirect.co.uk/pub/media/catalog/product/cache/edd36882d568ffd07fecd50ce5cdaf37/r/f/rfidroundstickers.jpg)

(credit: idcardsdirect.co.uk)

---

Mifare Classic Rectangular sticker

![image](https://user-images.githubusercontent.com/72751518/165159270-925bf007-60df-452b-847b-fed67eda325d.png)

(credit: amazon.co.uk)

---

Mifare Classic Data Structures
![image](https://user-images.githubusercontent.com/72751518/165160898-6f5462c9-7ae1-455b-b4c9-ece63887bc39.png)
