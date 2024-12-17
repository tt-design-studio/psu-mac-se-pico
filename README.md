## Mac SE Pico PSU Project "T.N.T." Overview

[Purchase bare board link](https://www.tindie.com/products/ttdesign/diy-macintosh-se30-se-pico-power-supply-board/)

[Purchase completed assembly link](https://www.tindie.com/products/ttdesign/macintosh-mac-se30-se-pico-atx-power-supply/)

![](/images/PSU_SE_Pico_3D_Rendering.jpg)

This project is for a design of a modern replacement of the AC/DC power supply board for the Apple Macintosh SE/30 and SE using all new components. It is mainly intended to be a DIY project to build on your own.

This board uses a Pico ATX power supply and uses an internal AC/DC converter to keep the stock machine functioning as it was designed. It keeps the original switch and AC power plug so that the machine doesn't need any external modifications and the changes are kept withing the power supply enclosure.

What follows are some notes to aid in the build configuration and component selection. 

## AC-DC Power Supply Specs

Here's a table of the build options for the different Mean Well IRM modules and their voltage rails.

| Voltage Rail |IRM-90-12 | IRM-60-12 |
| ----- | ------------- | ------- |
| +12 V |  6.67 A    | 5 A |
Table 1: PSU Module Specs **IRM-90-12 is recommended**

Note, the power draw on the -12 V rail in a typical SE/30 setup is ~ 0.1 A.

## Supplier Project Links

The project / BOM links contain connector parts for all three configurations, so you can omit the ones you don't need.

### Board versions 0.2

- [Digikey](https://www.digikey.com/en/mylists/list/SZG5HO0RRM)

- Mouser (Pending)

### Pico ATX Power supply

The design was tested with a couple of different RGEEK power supplies, including the 20-pin version. The connector is compatible with 20 or 24 pin pico ATX PSUs. [Mini-Box](https://www.mini-box.com) is one of the early original designers of this form factor and may be higher quality. There are some possibly counterfeit listings in places (confirmed by Mini-Box), so it may be best to order direct from them or ask them if a particular listing is genuine.

### Cable Assembly

#### Modular cable assembly (connector on both ends)

The modular cable approach tries to balance the ease of assembly with the standard practice of using a crimped wire and terminal pin for wire to board applications. If an issue develops with the cable, it can be more easily replaced. The trade-off is it adds two components for the connectors and some small additional contact resistance.

- [Mouser]()
- [Digikey]()

#### Direct board soldering

Note: Typically PSU stranded wires have a terminal crimped to the wire end ([example](https://www.digikey.com/en/products/detail/te-connectivity-amp-connectors/170338-1/1861092)) and then the terminal is soldered to the board. This prevents solder from wicking into the cable which weakens the cable and the terminal provides strain relief by holding onto the insulator.

Molex 10 pin, 225 mm, 18 AWG, single ended for soldering wires directly to the board

- [Mouser](https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=94fdc6ba0d)

- [Digikey](https://www.digikey.com/en/mylists/list/Y2ULEIMUVL)

## BOM and Assembly Notes

| Note No. | BOM Notes                                                    |
| -------- | ------------------------------------------------------------ |
| 1        | You can probably transfer the working fuse from the old PCBA if you would like (v0.3 note: the ASTEC variant fuse is physically larger and cannot be reused), or use one like the one suggested in the cart link. |
| 2        | The board is designed for all new components, so the old Sony connector does not need to be harvested. There are two AC connector options for the type of PSU chassis. J2 is for the Sony variant, which uses 3 pins directly soldered to the board. J3 is for Apple variant. For the the Apple variant, you may want to buy an extra J3 considering note 3. |
| 3        | One pin (out of the 4) is removed from J3 to create a keyed connector to prevent reversing the connection. Check your original board to see which pin is missing while using the locking tab for the orientation. An easy way to do remove the pin is to hold the connector body in a vise and heat the pin closer to the plastic base with a soldering iron while holding the pin with pliers. Pull the pin out when it starts to give, which will likely happen very quickly. Board version 0.5 allows you to use the board as a fixture by soldering the two pins and then removing the *poka-yoke pin*. |
| 4        | The Mean Well IRM-90-12 is interchangeable with IRM-60-12 |

## Power Cable Assembly

The PCB legend includes a voltage and color guide per the original PSU designs to help with assembly of the cable and confirming the voltages with a multimeter.

### 1. Connector Info

- **Connector Type:** Molex Mini-Fit Jr 5557 series
- **Part Number:** 0039012105
- **Number of Pins:** 10
- **Gender:** Receptacle (female)
- **Quantity:** 2 or 1 for direct soldering to board

### 2. Wire Specifications

- **Wire Gauge:** 18 AWG
- **Wire Type:** UL 1061
- **Wire Type:** Flexible multi-stranded
- **Length:** 20 cm (with connector on both ends) or 22.5-30 cm for a single connector with direct soldering to the board
- **Quantity:** 10 wires total per the color coding (if desired)

### 4. Terminal Specifications

- **Terminal Type:** Molex Mini-Fit Jr 5556 series
- **Gender:** Female
- **Part Number:** 0039000046
- **Quantity:** 20 (one for each wire end)

### 5. Pin-Out and Color Coding

| Pin Number | Signal Name | Wire Color |
| ---------- | ----------- | ---------- |
| 1          | GND         | Black      |
| 2          | GND         | Black      |
| 3          | GND         | Black      |
| 4          | +5V         | Orange     |
| 5          | +12V        | Yellow     |
| 6          | -12V        | Green      |
| 7          | GND         | Black      |
| 8          | GND         | Black      |
| 9          | +5V         | Orange     |
| 10         | +12V        | Red        |

Table 2: Pin / signal / wire color code listing for both ends of the harnesss.

![](/images/cable_harness_layout.png)
