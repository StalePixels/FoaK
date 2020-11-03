'Font of all Knowledge' - Native File Format (.FOK)
=

Abstract
-

.FOK files are intended for sharing complete sets of fontdata between other users and applications. They are _not_ intended for direct inclusion in any software, except for those expecting to manipulate the file content.

Binary Layout
-

| Data                 	| Description                             	| Offset 	|
|---------------------:	|-----------------------------------------	|-------:	|
| FOK                  	| 3Byte file identifier, "FOK"            	| 0x0000 	|
| 0x01                 	| 1Byte, format version identifier        	| 0x0003 	|
| 0x00                 	| 1Byte, reserved, always zero            	| 0x0004 	|
| FoaK001a             	| 8Byte ID of app that generated the file 	| 0x0005 	|
| Description of Font  	| 20Byte display name for the font        	| 0x000D 	|
| 0x00                 	| 1Byte, reserved, always zero            	| 0x0021 	|
| 0x0F                 	| 1Byte, number of palette entries        	| 0x0022 	|
| [uint16_t]           	| 2Byte, bitmask to generate 1bit fonts   	| 0x0023 	|
| [Font Bitmap Data] 	| 4096Byte, 4bpp font bitmap memdump      	| 0x0025 	|
| Palette Name #0      	| 8Byte, Palette Description              	| 0x1025 	|
| Palette Data #0      	| 512Byte, Palette Data                   	| 0x102D 	|

Palette Name and Palette Data repeat, as dictated by Byte 34 (0x22) - the Palette Entry Count.