


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

Low frequency credentials can be handled by Flipper Zero's **125kHz** application, for additional information see:
- https://docs.flipperzero.one/rfid
- https://github.com/equipter/flipper-knowledgebase/tree/main/125khz-rfid

High frequency credentials can be handled by Flipper Zero's **NFC** application, for additional information see:
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
</table>
</td>
<td>
<a href="https://www.idesco.com/picts/products/hid-proxcard-ii-1326.png"><img src="https://www.idesco.com/picts/products/hid-proxcard-ii-1326.png" alt="HID Prox Fob"></a>
<a href="https://m.media-amazon.com/images/I/71LWBXxiF5L._AC_SL1500_.jpg"><img src="https://m.media-amazon.com/images/I/71LWBXxiF5L._AC_SL1500_.jpg" alt="HID Prox Fob"></a>
</td>
<td>Additional protocols are technically comatbile with Flipper Zero and may be added in the future. </td>
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
<a href="https://globalgatecontrols.com/app/uploads/2020/02/fpcrd_Indala_26_Bit_FlexPass_Proximity_Card_Front_1.png"><img src="https://globalgatecontrols.com/app/uploads/2020/02/fpcrd_Indala_26_Bit_FlexPass_Proximity_Card_Front_1.png" alt="Indala Clamshell"></a>
<a href="https://cdn.shopify.com/s/files/1/0173/0271/6516/products/Indala_Fob_A_1024x1024.png?v=1547950599"><img src="https://cdn.shopify.com/s/files/1/0173/0271/6516/products/Indala_Fob_A_1024x1024.png?v=1547950599" alt="Indala Fob"></a>
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
</table>

## Cloning Low Frequency Credentials
For supported types, Flipper Zero also supports writing stored Low Frequency credentials to rewriteable cards/fobs. The most common and preferred type of rewriteable device are based on the **T5577** chip. These devices can come in all form factors (fob, card, implant, etc) but all work the same.

T5577 devices can be sourced online on Amazon, eBay, AliExpress, etc.

A popular brand is "Yarongtech", which is available on Amazon.


# High Frequency Credentials
((HF Hardware Description))

There are also a wide variety of High Frequency/NFC credential types. These types of credentials are common for:

 - Transit Passes/Cards
 - Hotel Keys

## Payment Cards
Credit/debit cards also use the NFC protocol, but operate on a specific system called "EMV". See xxx for additional information on EMV.

## High Frequency Protocols
((Protocols Introduction))
<table>
<tbody>
<tr>
<th>Brand</th>
<th>Name</th>
<th>Common Uses</th>
<th>Encryption</th>
<th>Flipper Zero Status</th>
<th>Future Plans</th>
</tr>
<tr>
<td>NXP</td>
<td>Mifare Classic</td>
<td>
<ul>
<li>Hotel Room Keys</li>
<li>Transit System Cards</li>
</td>
<td>Unencrypted</td>
<td>
<table>
<tr><td><i>Read: </i><br>Partially Supported</td></tr>
<tr><td><i>Write: </i><br>Not Supported</td></tr>
<tr><td><i>Emulate: </i><br>Not Supported</td></tr>
</table>
</td>
<td>Emulation currently in development</td>
</tr>
</table>



# FAQ Status
 - **WORK IN PROGRESS**
 - **NOT VERIFIED**
 - Maintainers:
	 - @forbiddenpineapple
# Disclaimer
Please use this **information** responsibly, only **you** are responsible for **your** actions.
