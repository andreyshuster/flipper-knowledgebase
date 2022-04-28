



# "Access Cards" 101 (Work In Progress)

Flipper Zero is very skilled at reading access cards (referred to here as "Credentials") of all types. This FAQ will discuss the various types of access credentials and Flipper Zero's capabilities.

# Access Credential Types
![Flipper with HF and LF Credentials](https://blog.flipperzero.one/content/images/size/w2000/2021/09/Untitled-183831--1-.jpg)

There are two main categories of access credentials, both of which are supported by Flipper Zero: 

 - Low Frequency (LF, 125kHz)
 - High Frequency (NFC, 13.56Mhz)

## Identifying LF vs HF Credentials
The easiest way to identify a low frequency 125KHz credential vs an NFC credential is to look inside (non-destructively of course). The Flipper Zero blog makes a good description of this: [Flipper Zero RFID Blog Post](https://blog.flipperzero.one/rfid/). 

In summary: by looking thru the credential with a high powered flashlight, you may be able to tell if the tag is low or high frequency based on the shape of the antenna:

![LF vs HF Card Antennas](https://habrastorage.org/r/w1560/webt/hi/dc/ki/hidckijb-wsscmuqutxmkeeuama.jpeg)

Low Frequency credentials can be handled by Flipper Zero's **125kHz** application, for additional information see:
- https://docs.flipperzero.one/rfid
- https://github.com/equipter/flipper-knowledgebase/tree/main/125khz-rfid

High Frequency credentials can be handled by Flipper Zero's **NFC** application, for additional information see:
- https://docs.flipperzero.one/nfc
- https://github.com/equipter/flipper-knowledgebase/tree/main/NFC

# Low Frequency Credentials
Flipper Zero's hardware includes a 125kHz transmitter and receiver which is connected directly to the MCU's GPIO. Flipper Zero directly interprets 125kHz data.

Low Frequency credentials are commonly used for:

 - Office Buildings
 - Apartment Buildings

## Low Frequency Protocols
There are an extremely large number of Low Frequency access card protocols, encodings, and modulations. 

Flipper Zero's official 125kHz documentation lists the official supported credentials: [Flipper Zero RFID Documentation](https://docs.flipperzero.one/rfid)

The table below lists some of the common types of Low Frequency credential types and their current status:

<table>
<tbody>
<tr>
<th>Brand</th>
<th>Name</th>
<th>Protocols and Status</th>
<th>Photos</th>
<th>Future Plans</th>
<tr>
<td>HID</td>
<td>Prox</td>
<td>
<table align="center" style="width:100%">
<tr>
<th>Protocol</th>
<th>Read</th>
<th>Write</th>
<th>Emulate</th>
</tr>
<tr>
<td>H10301 (HID26/HID PROX II)</td>
<td>Yes</td>
<td>Yes</td>
<td>Yes</td>
</tr>
<tr>
<td>Others</td>
<td>No</td>
<td>No</td>
<td>No</td>
</tr>
</table>
</td>
<td>
<a href="https://www.idesco.com/picts/products/hid-proxcard-ii-1326.png"><img src="https://www.idesco.com/picts/products/hid-proxcard-ii-1326.png" alt="HID Prox Fob"></a>
<a href="https://m.media-amazon.com/images/I/71LWBXxiF5L._AC_SL1500_.jpg"><img src="https://m.media-amazon.com/images/I/71LWBXxiF5L._AC_SL1500_.jpg" alt="HID Prox Fob"></a>
</td>
<td>Additional protocols are technically comatbile with Flipper Zero and may be added in the future. </td>
</tr>
<tr>
<td>HID</td>
<td>iClass</td>
<td>
iClass contain both Low Frequency and High Frequency chips, some systems may use LF or HF and some may use both.<br>
For LF, the system is similar to HID Prox (above).<br>
For HF, see the iClass row under High Frequency credentials.
</td>
<td>
<a href="https://www.hidglobal.com/sites/default/files/iclass_clamshell2.png"><img src="https://www.hidglobal.com/sites/default/files/iclass_clamshell2.png" alt="HID iClass Fob"></a>
<a href="https://www.hidglobal.com/sites/default/files/iclass_keyfob-ii_0.png"><img src="https://www.hidglobal.com/sites/default/files/iclass_keyfob-ii_0.png" alt="HID iClass Fob"></a>
</td>
<td>See rows for HID Prox and HID iClass.</td>
</tr>
<tr>
<td>Motorola/HID</td>
<td>Indala</td>
<td align="center">
<table style="width:100%">
<tr>
<th>Protocol</th>
<th>Read</th>
<th>Write</th>
<th>Emulate</th>
</tr>
<tr>
<td>I40134</td>
<td>Yes</td>
<td>Yes</td>
<td>Yes</td>
</tr>
</table>
</td>
<td>
<a href="https://cdn.shopify.com/s/files/1/0173/0271/6516/products/Indala_Fob_A_1024x1024.png?v=1547950599"><img src="https://cdn.shopify.com/s/files/1/0173/0271/6516/products/Indala_Fob_A_1024x1024.png?v=1547950599" alt="Indala Fob"></a>
<a href="https://globalgatecontrols.com/app/uploads/2020/02/fpcrd_Indala_26_Bit_FlexPass_Proximity_Card_Front_1.png"><img src="https://globalgatecontrols.com/app/uploads/2020/02/fpcrd_Indala_26_Bit_FlexPass_Proximity_Card_Front_1.png" alt="Indala Clamshell"></a>
</td>
<td>Additional protocols are technically compatible with Flipper Zero and may be added in the future. </td>
</tr>
<tr>
<td>EM-Marin</td>
<td align="center" colspan="2">
<table style="width:100%">
<tr>
<th>Chip</th>
<th>Read</th>
<th>Write</th>
<th>Emulate</th>
</tr>
<tr>
<td>EM4100</td>
<td>Yes</td>
<td>Yes</td>
<td>Yes</td>
</tr>
</table>
</td>
<td>
</td>
<td>
</td>
</tr>
<tr>
<td colspan=2>AWID</td>
<td align="center">
<table style="width:100%">
<tr>
<th>Protocol</th>
<th>Read</th>
<th>Write</th>
<th>Emulate</th>
</tr>
<tr>
<td>ALL</td>
<td>No</td>
<td>No</td>
<td>No</td>
</tr>
</table>
</td>
<td>
<a href="https://cdn.adiglobaldistribution.us/adina/1018890628_lg.jpg"><img src="https://cdn.adiglobaldistribution.us/adina/1018890628_lg.jpg" alt="AWID KT Key Fob"></a>
<a href="https://globalgatecontrols.com/app/uploads/2020/02/CS_AWID_CS_Proximity_Card_Front_1.png"><img src="https://globalgatecontrols.com/app/uploads/2020/02/CS_AWID_CS_Proximity_Card_Front_1.png" alt="AWID Key Card"></a>
</td>
<td>LF AWID cards are technically compatible with Flipper Zero's hardware and may be supported in the future. </td>
</tr>
</table>

## Cloning Low Frequency Credentials
For supported types, Flipper Zero also supports writing stored Low Frequency credentials to rewriteable cards/fobs. The most common and preferred type of rewriteable device are based on the **T5577** chip. These devices can come in all form factors (fob, card, implant, etc) but all work the same.

T5577 devices can be sourced online on Amazon, eBay, AliExpress, etc.

A popular brand is "Yarongtech", which is available on Amazon.


# High Frequency Credentials
Flipper Zero's hardware includes a dedicated High Frequency/NFC chip: the [ST25R3916](https://www.st.com/resource/en/datasheet/st25r3916.pdf). This chip handles the communication with High Frequency devices in conjunction with the MCU.

There are also a wide variety of High Frequency/NFC credential types. These types of credentials are common for:

 - Transit Passes/Cards
 - Hotel Keys

## Card Structure/UIDs
High Frequency cards are different than Low Frequency cards. While Low Frequency cards are often "dumb" and just contain a single identifying number which they transmit to the receiver, High Frequency cards are often equipped with more intelligent chips which store data and provide other functions (including encryption).

A large portion of HF cards are based around the ISO 14443 standard (with the exception of some MIFARE types). All ISO 14443 cards have what is called a "UID" or unique ID. This is in essence the card's serial number and is never encrypted (it may even be printed on the card exterior). Flipper Zero should be able to read the UID of most HF cards and emulate the UID. Some rudimentary High Frequency access control systems use only the UID for authentication and can thus easily work with Flipper Zero.

Additional data is available on cards beyond the UID, but this data is accessed using different protocols and may be encrypted or otherwise unreadable without specific keys or programming.



## Payment Cards
Credit/debit cards also use the NFC protocol, but operate on a specific system called "EMV". See xxx for additional information on EMV.

## High Frequency Protocols
There are an wide variety of High Frequency access card protocols. 

Flipper Zero's official NFC documentation lists the official supported credentials: [Flipper Zero NFC Documentation](https://docs.flipperzero.one/nfc)

The table below lists some of the common types of High Frequency credential types and their current status:
<table>
<tbody>
<tr>
<th>Brand</th>
<th>Name</th>
<th>Common Uses</th>
<th>Encryption</th>
<th>Read</th>
<th>Write</th>
<th>Emulate</th>
<th>Future Plans</th>
</tr>
<tr>
<td>NXP</td>
<td>MIFARE Classic</td>
<td>
<ul>
<li>Hotel Room Keys</li>
<li>Older Transit System Cards</li>
</td>
<td>Unencrypted</td>
<td>Partial</td>
<td>No</td>
<td>In Progress</td>
<td>Emulation currently in development.</td>
</tr>
<tr>
<td>NXP</td>
<td>MIFARE DESFIRE</td>
<td>
<ul>
<li>Secure Access Control Systems</li>
<li>Some Newer Transit System Cards</li>
</ul>
</td>
<td><b>Very</b> Encrypted</td>
<td>UID Only</td>
<td>No</td>
<td>No</td>
<td>Likely to never be supported due to encryption.</td>
</tr>
<tr>
<td>NXP</td>
<td>MIFARE Plus (X and S)</td>
<td>
<ul>
<li>Secure Access Control Systems</li>
<li>Some Newer Transit System Cards</li>
</ul>
</td>
<td>Encrypted (AES-128)</td>
<td>UID Only</td>
<td>No</td>
<td>No</td>
<td>Likely to never be supported due to encryption.</td>
</tr>
<tr>
<td>NXP</td>
<td>MIFARE Ultralight</td>
<td>
</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>HID</td>
<td>iClass</td>
<td>
Access Control Systems
</td>
<td></td>
<td>No</td>
<td>No</td>
<td>No</td>
<td></td>
</tr>
<tr>
<td>HID</td>
<td>iClass SE</td>
<td>
Access Control Systems
</td>
<td></td>
<td>No</td>
<td>No</td>
<td>No</td>
<td></td>
</tr>
<tr>
<td>HID</td>
<td>iClass SEOS</td>
<td>
Access Control Systems
</td>
<td></td>
<td>No</td>
<td>No</td>
<td>No</td>
<td></td>
</tr>
</table>



# FAQ Status
 - **WORK IN PROGRESS**
 - **NOT VERIFIED**
 - Maintainers:
	 - @forbiddenpineapple
# Disclaimer
Please use this **information** responsibly, only **you** are responsible for **your** actions.
