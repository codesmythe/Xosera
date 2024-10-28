# Xosera - Register Quick Reference

- [Xosera - Register Quick Reference](#xosera---register-quick-reference)
    - [Xosera Main Registers (XM Registers)](#xosera-main-registers-xm-registers)
        - [**`XM_SYS_CTRL`** 0x0 (R/W+) - System Control](#xm_sys_ctrl-0x0-rw---system-control)
        - [**`XM_INT_CTRL`** 0x1 (R/W+) - Interrupt Control](#xm_int_ctrl-0x1-rw---interrupt-control)
        - [**`XM_TIMER`** 0x2 (R/W) - Timer Functions](#xm_timer-0x2-rw---timer-functions)
        - [**`XM_RD_XADDR`** 0x3 (R/W+) - XR Read Address](#xm_rd_xaddr-0x3-rw---xr-read-address)
        - [**`XM_WR_XADDR`** 0x4 (R/W) - XR Write Address](#xm_wr_xaddr-0x4-rw---xr-write-address)
        - [**`XM_XDATA`** 0x5 (R+/W+) - XR Read/Write Data](#xm_xdata-0x5-rw---xr-readwrite-data)
        - [**`XM_RD_INCR`** 0x6 (R/W) - Increment for VRAM Read Address](#xm_rd_incr-0x6-rw---increment-for-vram-read-address)
        - [**`XM_RD_ADDR`** 0x7 (R/W+) - VRAM Read Address](#xm_rd_addr-0x7-rw---vram-read-address)
        - [**`XM_WR_INCR`** 0x8 (R/W) - Increment for VRAM Write Address](#xm_wr_incr-0x8-rw---increment-for-vram-write-address)
        - [**`XM_WR_ADDR`** 0x9 (R/W) - VRAM Write Address](#xm_wr_addr-0x9-rw---vram-write-address)
        - [**`XM_DATA`** 0xA (R+/W+) - VRAM Read/Write Data](#xm_data-0xa-rw---vram-readwrite-data)
        - [**`XM_DATA_2`** 0xB (R+/W+) - VRAM Read/Write Data (2nd)](#xm_data_2-0xb-rw---vram-readwrite-data-2nd)
        - [**`XM_PIXEL_X`** 0xC (-/W+) - X coordinate for pixel addr/mask generation (also used to set `PIXEL_BASE`)](#xm_pixel_x-0xc--w---x-coordinate-for-pixel-addrmask-generation-also-used-to-set-pixel_base)
        - [**`XM_PIXEL_Y`** 0xD (-/W+) - Y coordinate for pixel addr/mask generation (also used to set `PIXEL_WIDTH`)](#xm_pixel_y-0xd--w---y-coordinate-for-pixel-addrmask-generation-also-used-to-set-pixel_width)
        - [**`XM_UART`** 0xE (R+/W+) - UART (DEPRECATED: not normally present)](#xm_uart-0xe-rw---uart-deprecated-not-normally-present)
        - [**`XM_FEATURE`** 0xF (R/-) - Xosera feature bits](#xm_feature-0xf-r----xosera-feature-bits)
  - [Xosera Extended Register / Extended Memory Region Summary](#xosera-extended-register--extended-memory-region-summary)
    - [Video Config and Control XR Registers](#video-config-and-control-xr-registers)
        - [**`XR_VID_CTRL`** 0x00 (R/W) - Border Color / Playfield Color-Swap](#xr_vid_ctrl-0x00-rw---border-color--playfield-color-swap)
        - [**`XR_COPP_CTRL`** 0x01 (R/W) - Copper Enable](#xr_copp_ctrl-0x01-rw---copper-enable)
        - [**`XR_AUD_CTRL`** 0x02 (R/W) - Audio Control](#xr_aud_ctrl-0x02-rw---audio-control)
        - [**`XR_SCANLINE`** 0x03 (R/W+) - current video scan line/trigger Xosera host CPU video interrupt](#xr_scanline-0x03-rw---current-video-scan-linetrigger-xosera-host-cpu-video-interrupt)
        - [**`XR_VID_LEFT`** 0x04 (R/W) - video display window left edge](#xr_vid_left-0x04-rw---video-display-window-left-edge)
        - [**`XR_VID_RIGHT`** 0x05 (R/W) - video display window right edge](#xr_vid_right-0x05-rw---video-display-window-right-edge)
        - [**`XR_POINTER_H`** 0x06 (-/W+) - pointer sprite H position](#xr_pointer_h-0x06--w---pointer-sprite-h-position)
        - [**`XR_POINTER_V`** 0x07 (-/W+) - pointer sprite V position and colormap select](#xr_pointer_v-0x07--w---pointer-sprite-v-position-and-colormap-select)
    - [Playfield A \& B Control XR Registers](#playfield-a--b-control-xr-registers)
        - [**`XR_Px_GFX_CTRL`** 0x10/0x18 (R/W) - playfield A/B (base/overlay) graphics control](#xr_px_gfx_ctrl-0x100x18-rw---playfield-ab-baseoverlay-graphics-control)
        - [**`XR_Px_TILE_CTRL`** 0x11/0x19 (R/W) - playfield A/B (base/overlay) tile control](#xr_px_tile_ctrl-0x110x19-rw---playfield-ab-baseoverlay-tile-control)
        - [**`XR_Px_DISP_ADDR`** 0x12/0x1A (R/W) - playfield A/B (base/overlay) display VRAM start address](#xr_px_disp_addr-0x120x1a-rw---playfield-ab-baseoverlay-display-vram-start-address)
        - [**`XR_Px_LINE_LEN`** 0x13/0x1B (R/W) - playfield A/B (base/overlay) display line word length](#xr_px_line_len-0x130x1b-rw---playfield-ab-baseoverlay-display-line-word-length)
        - [**`XR_Px_HV_FSCALE`** 0x14/0x1C (R/W) - playfield A/B (base/overlay) horizontal and vertical fractional scale](#xr_px_hv_fscale-0x140x1c-rw---playfield-ab-baseoverlay-horizontal-and-vertical-fractional-scale)
        - [**`XR_Px_H_SCROLL`** 0x15/0x1D (R/W) - playfield A/B (base/overlay) horizontal fine scroll](#xr_px_h_scroll-0x150x1d-rw---playfield-ab-baseoverlay-horizontal-fine-scroll)
        - [**`XR_Px_V_SCROLL`** 0x16/0x1E (R/W) - playfield A/B (base/overlay) vertical repeat and tile fine scroll](#xr_px_v_scroll-0x160x1e-rw---playfield-ab-baseoverlay-vertical-repeat-and-tile-fine-scroll)
        - [**`XR_Px_LINE_ADDR`** 0x17/0x1F (-/W) - playfield A/B (base/overlay) display VRAM next line address](#xr_px_line_addr-0x170x1f--w---playfield-ab-baseoverlay-display-vram-next-line-address)
    - [Bitmap Display Formats Summary](#bitmap-display-formats-summary)
      - [1-BPP Bitmap Display Format](#1-bpp-bitmap-display-format)
      - [4-BPP Bitmap Display Format](#4-bpp-bitmap-display-format)
      - [8-BPP Bitmap Display Format](#8-bpp-bitmap-display-format)
    - [Tile Display Formats Summary](#tile-display-formats-summary)
      - [1-BPP Tilemap Format (256 glyphs, 4-bit foreground/background color in upper byte)](#1-bpp-tilemap-format-256-glyphs-4-bit-foregroundbackground-color-in-upper-byte)
      - [1-BPP Tiledef Format (256 glyphs, 8x8 tile 4 words or 8x16 tile 8 words, even line in high byte, odd in low)](#1-bpp-tiledef-format-256-glyphs-8x8-tile-4-words-or-8x16-tile-8-words-even-line-in-high-byte-odd-in-low)
      - [4-BPP Tilemap Format (1024 glyphs, H/V tile mirror, 4-bit color index offset)](#4-bpp-tilemap-format-1024-glyphs-hv-tile-mirror-4-bit-color-index-offset)
      - [4-BPP Tiledef Format (1024 glyphs, each 8x8 tile 16 words like 8x8 4-BPP bitmap)](#4-bpp-tiledef-format-1024-glyphs-each-8x8-tile-16-words-like-8x8-4-bpp-bitmap)
      - [1-BPP-EXT Tilemap Format (2048 glyphs, forground invert, background 4-BPP color index)](#1-bpp-ext-tilemap-format-2048-glyphs-forground-invert-background-4-bpp-color-index)
      - [1-BPP-EXT Tilemap Format (2048 glyphs, each 16 words like 16x16 bitmap)](#1-bpp-ext-tilemap-format-2048-glyphs-each-16-words-like-16x16-bitmap)
    - [Color Memory ARGB Look-up and Playfield A B Blending](#color-memory-argb-look-up-and-playfield-a-b-blending)
      - [**`COLOR_A`** and **`COLOR_B`** colormap format](#color_a-and-color_b-colormap-format)
      - [Audio Generation XR Registers](#audio-generation-xr-registers)
        - [**`XR_AUD0_VOL`** 0x20/0x24/0x28/0x2C (-/W) - audio channel 0-3 left/right mix volume](#xr_aud0_vol-0x200x240x280x2c--w---audio-channel-0-3-leftright-mix-volume)
        - [**`XR_AUD0_PERIOD`** 0x21/0x25/0x29/0x2D (-/W) - audio channel 0-3 sample period](#xr_aud0_period-0x210x250x290x2d--w---audio-channel-0-3-sample-period)
        - [**`XR_AUD0_LENGTH`** 0x22/0x26/0x2A/0x2E (-/W) - audio channel 0-3 sample word length and VRAM/TILE memory](#xr_aud0_length-0x220x260x2a0x2e--w---audio-channel-0-3-sample-word-length-and-vramtile-memory)
        - [**`XR_AUD0_START`** 0x23/0x27/0x2B/0x2F (-/W) - audio channel 0-3 sample start address (in either VRAM/TILE)](#xr_aud0_start-0x230x270x2b0x2f--w---audio-channel-0-3-sample-start-address-in-either-vramtile)
      - [2D Blitter Engine XR Registers](#2d-blitter-engine-xr-registers)
        - [**`XR_BLIT_CTRL`** 0x40 (-/W) - control bits (transparency control, S const)](#xr_blit_ctrl-0x40--w---control-bits-transparency-control-s-const)
        - [**`XR_BLIT_ANDC`** 0x41 (-/W) - source term ANDC value constant](#xr_blit_andc-0x41--w---source-term-andc-value-constant)
        - [**`XR_BLIT_XOR`** 0x42 (-/W) - source term XOR value constant](#xr_blit_xor-0x42--w---source-term-xor-value-constant)
        - [**`XR_BLIT_MOD_S`** 0x43 (-/W) - modulo added to `BLIT_SRC_S` address at end of line](#xr_blit_mod_s-0x43--w---modulo-added-to-blit_src_s-address-at-end-of-line)
        - [**`XR_BLIT_SRC_S`** 0x44 (-/W) - source `S` term (read from VRAM address or constant value)](#xr_blit_src_s-0x44--w---source-s-term-read-from-vram-address-or-constant-value)
        - [**`XR_BLIT_MOD_D`** 0x45 (-/W) - modulo added to `BLIT_DST_D` address at end of line](#xr_blit_mod_d-0x45--w---modulo-added-to-blit_dst_d-address-at-end-of-line)
        - [**`XR_BLIT_DST_D`** 0x46 (-/W) - destination `D` VRAM write address](#xr_blit_dst_d-0x46--w---destination-d-vram-write-address)
        - [**`XR_BLIT_SHIFT`** 0x47 (-/W) - first and last word nibble masks and nibble shift](#xr_blit_shift-0x47--w---first-and-last-word-nibble-masks-and-nibble-shift)
        - [**`XR_BLIT_LINES`** 0x48 (-/W) - 15-bit number of lines high - 1 (1 to 32768)](#xr_blit_lines-0x48--w---15-bit-number-of-lines-high---1-1-to-32768)
        - [**`XR_BLIT_WORDS`** 0x49 (-/W+) - write queues operation, word width - 1 (1 to 65536, repeats `XR_BLIT_LINES` times)](#xr_blit_words-0x49--w---write-queues-operation-word-width---1-1-to-65536-repeats-xr_blit_lines-times)
  - [Video Synchronized Co-Processor "Copper" Info](#video-synchronized-co-processor-copper-info)
    - [Copper Instruction Set](#copper-instruction-set)
      - [Copper Pseudo Instructions (when using CopAsm, or C macros)](#copper-pseudo-instructions-when-using-copasm-or-c-macros)
      - [Notes on Copper Memory Access](#notes-on-copper-memory-access)
    - [Default TILE, COLOR and COPPER Memory Contents](#default-tile-color-and-copper-memory-contents)

### Xosera Main Registers (XM Registers)

##### **`XM_SYS_CTRL`** 0x0 (R/W+) - System Control

![SYS_CTRL register diagram](./pics/wd_XM_SYS_CTRL.svg)

##### **`XM_INT_CTRL`** 0x1 (R/W+) - Interrupt Control

![XM_INT_CTRL register diagram](./pics/wd_XM_INT_CTRL.svg)

##### **`XM_TIMER`** 0x2 (R/W) - Timer Functions

![XM_TIMER register diagram](./pics/wd_XM_TIMER.svg)

##### **`XM_RD_XADDR`** 0x3 (R/W+) - XR Read Address

![XM_RD_XADDR register diagram](./pics/wd_XM_RD_XADDR.svg)

 **XR Register / Memory Read Address**

##### **`XM_WR_XADDR`** 0x4 (R/W) - XR Write Address

![XM_WR_XADDR register diagram](./pics/wd_XM_WR_XADDR.svg)

##### **`XM_XDATA`** 0x5 (R+/W+) - XR Read/Write Data

![XM_XDATA register diagram](./pics/wd_XM_XDATA.svg)

##### **`XM_RD_INCR`** 0x6 (R/W) - Increment for VRAM Read Address

![XM_RD_INCR register diagram](./pics/wd_XM_RD_INCR.svg)

##### **`XM_RD_ADDR`** 0x7 (R/W+) - VRAM Read Address

![XM_RD_ADDR register diagram](./pics/wd_XM_RD_ADDR.svg)

##### **`XM_WR_INCR`** 0x8 (R/W) - Increment for VRAM Write Address

![XM_WR_INCR register diagram](./pics/wd_XM_WR_INCR.svg)

##### **`XM_WR_ADDR`** 0x9 (R/W) - VRAM Write Address

![XM_WR_ADDR register diagram](./pics/wd_XM_WR_ADDR.svg)

##### **`XM_DATA`** 0xA (R+/W+) - VRAM Read/Write Data

![XM_DATA register diagram](./pics/wd_XM_DATA.svg)

##### **`XM_DATA_2`** 0xB (R+/W+) - VRAM Read/Write Data (2<sup>nd</sup>)

![XM_DATA_2 register diagram](./pics/wd_XM_DATA.svg)

##### **`XM_PIXEL_X`** 0xC (-/W+) - X coordinate for pixel addr/mask generation (also used to set `PIXEL_BASE`)

![XM_PIXEL_X register diagram](./pics/wd_XM_PIXEL_X.svg)

##### **`XM_PIXEL_Y`** 0xD (-/W+) - Y coordinate for pixel addr/mask generation (also used to set `PIXEL_WIDTH`)

![XM_PIXEL_Y register diagram](./pics/wd_XM_PIXEL_Y.svg)

##### **`XM_UART`** 0xE (R+/W+) - UART (DEPRECATED: not normally present)

![XM_UART register diagram](./pics/wd_XM_UART.svg)

##### **`XM_FEATURE`** 0xF (R/-) - Xosera feature bits

![XM_FEATURE register diagram](./pics/wd_XM_FEATURE.svg)

___

## Xosera Extended Register / Extended Memory Region Summary

| XR Region Name    | XR Region Range | R/W | Description                                   |
|-------------------|-----------------|-----|-----------------------------------------------|
| XR video config   | 0x0000-0x0007   | R/W | config XR registers                           |
| XR playfield A    | 0x0010-0x0017   | R/W | playfield A XR registers                      |
| XR playfield B    | 0x0018-0x001F   | R/W | playfield B XR registers                      |
| XR audio control  | 0x0020-0x002F   | -/W | audio channel XR registers                    |
| XR blit engine    | 0x0040-0x0049   | -/W | 2D-blit engine XR registers                   |
| `XR_TILE_ADDR`    | 0x4000-0x53FF   | R/W | 5KW 16-bit tilemap/tile storage memory        |
| `XR_COLOR_A_ADDR` | 0x8000-0x80FF   | R/W | 256W 16-bit color A lookup memory (0xARGB)    |
| `XR_COLOR_B_ADDR` | 0x8100-0x81FF   | R/W | 256W 16-bit color B lookup memory (0xARGB)    |
| `XR_POINTER_ADDR` | 0x8200-0x82FF   | -/W | 256W 16-bit 32x32 4-BPP pointer sprite bitmap |
| `XR_COPPER_ADDR`  | 0xC000-0xC5FF   | R/W | 1.5KW 16-bit copper memory                    |

___

### Video Config and Control XR Registers

##### **`XR_VID_CTRL`** 0x00 (R/W) - Border Color / Playfield Color-Swap

![XR_VID_CTRL register diagram](./pics/wd_XR_VID_CTRL.svg)

##### **`XR_COPP_CTRL`** 0x01 (R/W) - Copper Enable

![XR_COPP_CTRL register diagram](./pics/wd_XR_COPP_CTRL.svg)

##### **`XR_AUD_CTRL`** 0x02 (R/W) - Audio Control

![XR_AUD_CTRL register diagram](./pics/wd_XR_AUD_CTRL.svg)

##### **`XR_SCANLINE`** 0x03 (R/W+) - current video scan line/trigger Xosera host CPU video interrupt

![XR_SCANLINE register diagram](./pics/wd_XR_SCANLINE.svg)

##### **`XR_VID_LEFT`** 0x04 (R/W) - video display window left edge

![XR_VID_LEFT register diagram](./pics/wd_XR_VID_LEFT.svg)

##### **`XR_VID_RIGHT`** 0x05 (R/W) - video display window right edge  

![XR_VID_RIGHT register diagram](./pics/wd_XR_VID_RIGHT.svg)

##### **`XR_POINTER_H`** 0x06 (-/W+) - pointer sprite H position

![XR_POINTER_H register diagram](./pics/wd_XR_POINTER_H.svg)

##### **`XR_POINTER_V`** 0x07 (-/W+) - pointer sprite V position and colormap select

![XR_POINTER_V register diagram](./pics/wd_XR_POINTER_V.svg)

**0x08-0x0F `XR_UNUSED_0x` (-/- ) - Unused Registers**

___

### Playfield A & B Control XR Registers

##### **`XR_Px_GFX_CTRL`** 0x10/0x18 (R/W) - playfield A/B (base/overlay) graphics control  

![XR_Px_GFX_CTRL register diagram](./pics/wd_XR_Px_GFX_CTRL.svg)

##### **`XR_Px_TILE_CTRL`** 0x11/0x19 (R/W) - playfield A/B (base/overlay) tile control  

![XR_Px_TILE_CTRL register diagram](./pics/wd_XR_Px_TILE_CTRL.svg)

##### **`XR_Px_DISP_ADDR`** 0x12/0x1A (R/W) - playfield A/B (base/overlay) display VRAM start address  

![XR_Px_DISP_ADDR register diagram](./pics/wd_XR_Px_DISP_ADDR.svg)

##### **`XR_Px_LINE_LEN`** 0x13/0x1B (R/W) - playfield A/B (base/overlay) display line word length  

![XR_Px_LINE_LEN register diagram](./pics/wd_XR_Px_LINE_LEN.svg)

##### **`XR_Px_HV_FSCALE`** 0x14/0x1C (R/W) - playfield A/B (base/overlay) horizontal and vertical fractional scale  

![XR_Px_HV_FSCALE register diagram](./pics/wd_XR_Px_HV_FSCALE.svg)

##### **`XR_Px_H_SCROLL`** 0x15/0x1D (R/W) - playfield A/B (base/overlay) horizontal fine scroll  

![XR_Px_H_SCROLL register diagram](./pics/wd_XR_Px_H_SCROLL.svg)

##### **`XR_Px_V_SCROLL`** 0x16/0x1E (R/W) - playfield A/B (base/overlay) vertical repeat and tile fine scroll  

![XR_Px_V_SCROLL register diagram](./pics/wd_XR_Px_V_SCROLL.svg)

##### **`XR_Px_LINE_ADDR`** 0x17/0x1F (-/W) - playfield A/B (base/overlay) display VRAM next line address  

![XR_Px_LINE_ADDR register diagram](./pics/wd_XR_Px_LINE_ADDR.svg)

### Bitmap Display Formats Summary

Bitmap display data starts at the VRAM address`XR_Px_DISP_ADDR`, and has no alignment restrictions.

#### 1-BPP Bitmap Display Format

![1-BPP bitmap diagram](./pics/wd_1-bpp_bitmap_word.svg)

#### 4-BPP Bitmap Display Format

![4-BPP bitmap diagram](./pics/wd_4-bpp_bitmap_word.svg)

#### 8-BPP Bitmap Display Format

![8-BPP bitmap diagram](./pics/wd_8-bpp_bitmap_word.svg)

### Tile Display Formats Summary

Tile indices and attribute map display data starts at `XR_Px_DISP_ADDR` in either VRAM or TILEMEM (TILEMEM selected with `DISP_TILEMEM` bit in `XR_Px_TILE_CTRL`).  There are no alignment requirements for a tile (but even/odd address affects `GFX_1_BPP_EXT` tile half)

The tile bitmap definitions start at the aligned address specified in `TILEBASE` bits set in `XR_Px_TILE_CTRL` in TILEMEM or VRAM (VRAM selected with `TILE_VRAM` in `XR_Pßx_TILE_CTRL`).  The tileset address should be aligned based on the power of two greater than the size of the maximum glyph index used. When using all possible glyphs in a tileset, alignment would be as follows:

| BPP             | Size  | Words Per Tile | Glyphs | Word Alignment  |
|-----------------|-------|----------------|--------|-----------------|
| `GFX_1_BPP`     | 8x8   | 4 words        | 256    | 0x0400 boundary |
| `GFX_1_BPP`     | 8x16  | 8 words        | 256    | 0x0800 boundary |
| `GFX_4_BPP`     | 8x8   | 16 words       | 1024   | 0x4000 boundary |
| `GFX_1_BPP_EXT` | 16x16 | 32 words       | 2048   | 0x8000 boundary |

#### 1-BPP Tilemap Format (256 glyphs, 4-bit foreground/background color in upper byte)

![1-BPP tilemap diagram](./pics/wd_1-bpp_tile_word.svg)

#### 1-BPP Tiledef Format (256 glyphs, 8x8 tile 4 words or 8x16 tile 8 words, even line in high byte, odd in low)

![1-BPP tile definition diagram](./pics/wd_1-bpp_tile_def.svg)

#### 4-BPP Tilemap Format (1024 glyphs, H/V tile mirror, 4-bit color index offset)

![4-BPP tilemap diagram](./pics/wd_n-bpp_tile_word.svg)

#### 4-BPP Tiledef Format (1024 glyphs, each 8x8 tile 16 words like 8x8 4-BPP bitmap)

![4-BPP bitmap diagram](./pics/wd_4-bpp_bitmap_word.svg)

#### 1-BPP-EXT Tilemap Format (2048 glyphs, forground invert, background 4-BPP color index)

>NOTE: 1-BPP-EXT tilemap still uses 8x16 sized tiles.  Which half of 16x16 tiledef is displayed is based on tilemap address low-bit (so normally each character index is repeated twice in both even and odd columns).

![1-BPP extended diagram](./pics/wd_1-bpp-ext_tile_word.svg)

#### 1-BPP-EXT Tilemap Format (2048 glyphs, each 16 words like 16x16 bitmap)

![1-BPP-EXT tile definition diagram](./pics/wd_1-bpp-ext_tile_def.svg)

### Color Memory ARGB Look-up and Playfield A B Blending

| Name     | A Alpha Mode | A Alpha Value   | B Alpha Value | Blending Equation               | Blend effect                                |
|----------|--------------|-----------------|---------------|---------------------------------|---------------------------------------------|
| `BLEND`  | `00xx`       | inverse alpha B | alpha B       | $C_a (1-\alpha_b)+C_b \alpha_b$ | blend A with B using alpha B value          |
| `DARKEN` | `01xx`       | inverse alpha B | 0% alpha      | $C_a (1-\alpha_b)$              | blend A with black using alpha B value      |
| `ADD`    | `10xx`       | 100% alpha      | alpha B       | $C_a +C_b \alpha_b$             | additive blend A with B using alpha B value |
| `OPAQUE` | `11xx`       | 100% alpha      | 0% alpha      | $C_a$                           | color A only (playfield A on top)           |

#### **`COLOR_A`** and **`COLOR_B`** colormap format

Each `COLOR_A` and `COLOR_B` colormap has 256 16-bit entries in the following format:
![COLOR_A/B colormap register diagram](./pics/wd_colormap_word.svg)

___

#### Audio Generation XR Registers

##### **`XR_AUD0_VOL`** 0x20/0x24/0x28/0x2C (-/W) - audio channel 0-3 left/right mix volume  

![XR_AUDn_VOL register diagram](./pics/wd_XR_AUDn_VOL.svg)

##### **`XR_AUD0_PERIOD`** 0x21/0x25/0x29/0x2D (-/W) - audio channel 0-3 sample period

![XR_AUDn_PERIOD register diagram](./pics/wd_XR_AUDn_PERIOD.svg)

##### **`XR_AUD0_LENGTH`** 0x22/0x26/0x2A/0x2E (-/W) - audio channel 0-3 sample word length and VRAM/TILE memory

![XR_AUDn_LENGTH register diagram](./pics/wd_XR_AUDn_LENGTH.svg)

##### **`XR_AUD0_START`** 0x23/0x27/0x2B/0x2F (-/W) - audio channel 0-3 sample start address (in either VRAM/TILE)

![XR_AUDn_START register diagram](./pics/wd_XR_AUDn_START.svg)
___

#### 2D Blitter Engine XR Registers

##### **`XR_BLIT_CTRL`** 0x40 (-/W) - control bits (transparency control, S const)  

![XR_BLIT_CTRL register diagram](./pics/wd_XR_BLIT_CTRL.svg)

##### **`XR_BLIT_ANDC`** 0x41 (-/W) - source term ANDC value constant

![XR_BLIT_ANDC register diagram](./pics/wd_XR_BLIT_ANDC.svg)

##### **`XR_BLIT_XOR`** 0x42 (-/W) - source term XOR value constant

![XR_BLIT_XOR register diagram](./pics/wd_XR_BLIT_XOR.svg)

##### **`XR_BLIT_MOD_S`** 0x43 (-/W) - modulo added to `BLIT_SRC_S` address at end of line

![XR_BLIT_MOD_S register diagram](./pics/wd_XR_BLIT_MOD_S.svg)

##### **`XR_BLIT_SRC_S`** 0x44 (-/W) - source `S` term (read from VRAM address or constant value)

![XR_BLIT_SRC_S register diagram](./pics/wd_XR_BLIT_SRC_S.svg)

##### **`XR_BLIT_MOD_D`** 0x45 (-/W) - modulo added to `BLIT_DST_D` address at end of line

![XR_BLIT_MOD_D register diagram](./pics/wd_XR_BLIT_MOD_D.svg)

##### **`XR_BLIT_DST_D`** 0x46 (-/W) - destination `D` VRAM write address

![XR_BLIT_DST_D register diagram](./pics/wd_XR_BLIT_DST_D.svg)

##### **`XR_BLIT_SHIFT`** 0x47 (-/W) - first and last word nibble masks and nibble shift

![XR_BLIT_SHIFT register diagram](./pics/wd_XR_BLIT_SHIFT.svg)

##### **`XR_BLIT_LINES`** 0x48 (-/W) - 15-bit number of lines high - 1 (1 to 32768)

![XR_BLIT_LINES register diagram](./pics/wd_XR_BLIT_LINES.svg)

##### **`XR_BLIT_WORDS`** 0x49 (-/W+) - write queues operation, word width - 1 (1 to 65536, repeats `XR_BLIT_LINES` times)

![XR_BLIT_WORDS register diagram](./pics/wd_XR_BLIT_WORDS.svg)
___

## Video Synchronized Co-Processor "Copper" Info

| Video Mode | Aspect | Full res.  | H off-left | H visible   | V visible | V off-bottom |
|------------|--------|------------|------------|-------------|-----------|--------------|
| 640 x 480  | 4:3    | 800 x 525  | 0 to 159   | 160 to 799  | 0 to 479  | 480 to 524   |
| 848 x 480  | 16:9   | 1088 x 517 | 0 to 239   | 240 to 1079 | 0 to 479  | 480 to 516   |

### Copper Instruction Set

| Copper Assembly             | Opcode Bits           | B | # | ~  | Description                                         |
|-----------------------------|-----------------------|---|---|----|-----------------------------------------------------|
| `SETI`   *xadr14*,`#`*im16* | `rr00 oooo oooo oooo` | B | 2 | 4  | sets [xadr14] &larr; to #val16                      |
| > *im16* *value*            | `iiii iiii iiii iiii` | - | - | -  | *(im16, 2<sup>nd</sup> word of `SETI`)*             |
| `SETM`  *xadr16*,*cadr12*   | `--01 rccc cccc cccc` | B | 2 | 4  | sets [xadr16] &larr; to [cadr12]                    |
| > *xadr16* *address*        | `rroo oooo oooo oooo` | - | - | -  | *(xadr16, 2<sup>nd</sup> word of `SETM`)*           |
| `HPOS`   `#`*im11*          | `--10 0iii iiii iiii` |   | 1 | 4+ | wait until video H pos. >= *im11* or EOL            |
| `VPOS`   `#`*im11*          | `--10 1bii iiii iiii` |   | 1 | 4+ | wait until video V pos. >= *im11[9:0]*,`b`=blitbusy |
| `BRGE`   *cadd11*           | `--11 0ccc cccc cccc` |   | 1 | 4  | if (`B`==0) `PC` &larr; *cadd11*                    |
| `BRLT`   *cadd11*           | `--11 1ccc cccc cccc` |   | 1 | 4  | if (`B`==1) `PC` &larr; *cadd11*                    |

| Legend   | Description                                                                                              |
|----------|----------------------------------------------------------------------------------------------------------|
| `B`      | borrow flag, set true when `RA` < *val16* written (borrow after unsigned subtract)                       |
| `#`      | number of 16-bit words needed for instruction (1 or 2)                                                   |
| `~`      | number of copper cycles, always 4 unless a wait (each cycle is the time for one native pixel to output)  |
| *xadr14* | 2-bit XR region + 12-bit offset (1<sup>st</sup> word of `SETI`, destination XR address)                  |
| *im16*   | 16-bit immediate word (2<sup>nd</sup> word of `SETI`, the source value)                                  |
| *cadr12* | 11-bit copper address or register with bit [11] (1<sup>st</sup> word of `SETM`, source copper address)   |
| *xadr16* | 16-bit XR address (2<sup>nd</sup> word of `SETM`, destination XR address)                                |
| *im11*   | 11-bit value for `HPOS`, `VPOS` wait. With `VPOS` bit `[10]` indicates also stop waiting if blitter idle |
| *cadd11* | 11-bit copper program address for `BRGE`, `BRLT` branch opcodes                                          |

> :mag: **copper addresses** *cadr12*/*cadd11* bits`[15:14]` are ignored and copper memory is always used when reading or branching. When writing *xadr14*/*xadr16* bits `[15:14]` can be set to `11` (`XR_COPPER_ADDR` region) to write to copper memory. To help reduce confusion the CopAsm assembler sets `11`region bits in addresses for both reading and writing copper memory (even though these bits are ignored reading).

> :mag: **tilemem high addresses**  Note *xadr14* offset`[11:0]`is 12-bits and that is not enough to write to the last`0x400` words of the`XR_TILE_ADDR` area (`0x4000-0x53FF`) with`SETI`.  However, this area can be written to using a 16-bit word read from copper memory and `SETM` (which uses a full 16-bit *xadr16* destination).

**Copper addresses for memory mapped registers and operations:**

| Pseudo reg       | Copper Addr | Operation                                 | Description                                 |
|------------------|-------------|-------------------------------------------|---------------------------------------------|
| `RA` (read)      | `0x800`     | read value in `RA`, `B` unaltered         | return current value in `RA` register       |
| `RA` (write)     | `0x800`     | `RA` = *val16*, `B` =`0`                  | set `RA` to *val16*, clear `B` flag         |
| `RA_SUB` (write) | `0x801`     | `RA` = `RA` - *val16*, `B`=`RA` < *val16* | set `RA` to `RA` - *val16*, update `B` flag |
| `RA_CMP` (write) | `0x7FF`     | `B` = `RA` < *val16*                      | update B flag only (`RA` unaltered)         |

#### Copper Pseudo Instructions (when using CopAsm, or C macros)

In addition to above instructions, these synthetic instructions can help make code more clear (all map to a single copper instruction):

| Instruction                | Alias  | Words | Description                                                              |
|----------------------------|--------|-------|--------------------------------------------------------------------------|
| `MOVI` `#`*imm16*,*xadr14* | `SETI` | 2     | m68k order `SETI`, copy `#`*imm16* &rarr; *cadr12*                       |
| `MOVM` *cadr12*,*xadr16*   | `SETM` | 2     | m68k order`SETM`, copy *cadr12* &rarr; *xadr16*                          |
| `MOVE` `#`*imm16*,*xadr14* | `SETI` | 2     | m68k style `MOVE #` immediate copy `#`*imm16* &rarr; *xadr16*            |
| `MOVE` *cadr12*,*xadr16*   | `SETM` | 2     | m68k style `MOVE` memory copy *source* &rarr; *dest*                     |
| `LDI` `#`*imm16*           | `SETI` | 2     | Load `RA` register with value *imm16*, set `B`=`0`                       |
| `LDM` *cadr12*             | `SETM` | 2     | Load `RA` register with contents of memory *cadr12*, set `B`=`0`         |
| `STM` *xadr16*             | `SETM` | 2     | Store `RA` register contents into memory *xadr16*, set `B`=`0`           |
| `CLRB`                     | `SETM` | 2     | Store `RA` register into `RA`, set `B`=`0`                               |
| `SUBI` `#`*imm16*          | `SETI` | 2     | `RA` = `RA` - *imm16*, `B` flag updated                                  |
| `ADDI` `#`*imm16*          | `SETI` | 2     | `RA` = `RA` + *imm16*, `B` flag updated (for subtract of -*imm16*)       |
| `SUBM` *cadr12*            | `SETM` | 2     | `RA` = `RA` - contents of *cadr12*, `B` flag updated                     |
| `CMPI` `#`*imm16*          | `SETI` | 2     | test if `RA` < *imm16*, `B` flag updated (`RA` not altered)              |
| `CMPM` *cadr12*            | `SETM` | 2     | test it `RA` < contents of *cadr12*, `B` flag updated (`RA` not altered) |

#### Notes on Copper Memory Access

The copper can directly access the following Xosera resources:

- Write to any XR memory address or XR register, including:
  - `0x0000-0x004F` registers for video and control, playfield A/B, audio and blitter
  - `0x4000-0x53FF` tilemap, tile (font) or audio memory
  - `0x8000-0x80FF` colormap A memory
  - `0x8100-0x81FF` colormap B memory
  - `0x8200-0x82FF` pointer sprite memory (32x32x4-BPP)
  - `0xC000-0xC5FF` copper program/data memory

- Read from XR copper program/data memory `0xC000-0xC5FF`:
  - Reading and executing copper opcodes and operands fetched from copper `PC`
  - Reading data words from copper memory using `SETM` opcode

___

### Default TILE, COLOR and COPPER Memory Contents

| TILE address    | Description                                             |
|-----------------|---------------------------------------------------------|
| `0x4000-0x47FF` | 8x16 ST font (derived from Atari ST 8x16 font)          |
| `0x4800-0x4BFF` | 8x8 ST font (derived from Atari ST 8x8 font)            |
| `0x4C00-0x4FFF` | 8x8 PC font (derived from IBM CGA 8x8)                  |
| `0x5000-0x53FF` | 8x8 hexadecimal debug font (showing TILE number in hex) |
