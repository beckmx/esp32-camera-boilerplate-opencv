# ESP32 Camera Boilerplate with WIFI config

## General Information

This repository hosts the simplest way possible to setup a project using ESP-IDF v5.0 with the esp32-cam and with opencv.
You should be able to configure your development environment and move from there. The project has only 2 URLs

1) http://x.x.x.x/image
1) http://x.x.x.x/stream

They basically do what they describe, one take a still picture and the other performs streaming

Everything is inside a single UGLY file for the sole purpose of having a simple project where you can take code from.
### WIFI SSID and PWD

- EXAMPLE_ESP_WIFI_PASS
- EXAMPLE_ESP_WIFI_SSID

## How to RUN the project

clone this repo, and execute these commands
- cd esp32-camera-boilerplate-opencv
- cd examples
- idf.py set-target esp32
- idf.py build
- esptool.py -p /dev/tty.PORT -b 460800 --before default_reset --after hard_reset --chip esp32  write_flash --flash_mode dio --flash_size 4MB --flash_freq 80m 0x1000 build/bootloader/bootloader.bin 0x10000 build/partition_table/partition-table.bin 0x20000 build/camera_example.bin

Enjoy!

### Supported Sensor

| model   | max resolution | color type | output format                                                | Len Size |
| ------- | -------------- | ---------- | ------------------------------------------------------------ | -------- |
| OV2640  | 1600 x 1200    | color      | YUV(422/420)/YCbCr422<br>RGB565/555<br>8-bit compressed data<br>8/10-bit Raw RGB data | 1/4"     |
| OV3660  | 2048 x 1536    | color      | raw RGB data<br/>RGB565/555/444<br/>CCIR656<br/>YCbCr422<br/>compression | 1/5"     |
| OV5640  | 2592 x 1944    | color      | RAW RGB<br/>RGB565/555/444<br/>CCIR656<br/>YUV422/420<br/>YCbCr422<br/>compression | 1/4"     |
| OV7670  | 640 x 480      | color      | Raw Bayer RGB<br/>Processed Bayer RGB<br>YUV/YCbCr422<br>GRB422<br>RGB565/555 | 1/6"     |
| OV7725  | 640 x 480      | color      | Raw RGB<br/>GRB 422<br/>RGB565/555/444<br/>YCbCr 422         | 1/4"     |
| NT99141 | 1280 x 720     | color      | YCbCr 422<br/>RGB565/555/444<br/>Raw<br/>CCIR656<br/>JPEG compression | 1/4"     |
| GC032A  | 640 x 480      | color      | YUV/YCbCr422<br/>RAW Bayer<br/>RGB565                        | 1/10"    |
| GC0308  | 640 x 480      | color      | YUV/YCbCr422<br/>RAW Bayer<br/>RGB565                        | 1/6.5"   |
| GC2145  | 1600 x 1200    | color      | YUV/YCbCr422<br/>RAW Bayer<br/>RGB565                        | 1/5"     |
| BF3005  | 640 x 480      | color      | YUV/YCbCr422<br/>RAW Bayer<br/>RGB565                        | 1/4"     |
| BF20A6  | 640 x 480      | color      | YUV/YCbCr422<br/>RAW Bayer                                   | 1/10"    |
| SC101IOT| 1280 x 720     | color      | YUV/YCbCr422<br/>Raw RGB                                     | 1/4.2"   |
| SC030IOT| 640 x 480      | color      | YUV/YCbCr422<br/>RAW Bayer                                   | 1/6.5"   |
| SC031GS | 640 x 480      | monochrome | RAW MONO<br/>Grayscale                                       | 1/6"     |

