<div id="top"></div>

<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![GNU License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/dgtaheno/artillery-Genius">
    <img src="logo.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">Marlin 2.1.2 Firmware + TFT firmware for Artillery Genius 3D printer </h3>

  <p align="center">
    I decided that I needed to update my Artillery Genius 3-D printer firmware (Marlin + TFT) to the latest version, so what the heck, let´s do a custom firmware for my 3-D printer.
    <br />
    <a href="https://github.com/dgtaheno/artillery-Genius"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/dgtaheno/artillery-Genius">View Demo</a>
    ·
    <a href="https://github.com/dgtaheno/artillery-Genius/issues">Report Bug</a>
    ·
    <a href="https://github.com/dgtaheno/artillery-Genius/issues">Request Feature</a>
  </p>
</div>

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

<!-- ABOUT THE PROJECT -->

## About The Project

[![Product Name Screen Shot][product-screenshot]](https://github.com/dgtaheno)

My artillery Genius is working perfect but... I want to connect it with <a href="https://github.com/OctoPrint/">Octoprint</a> and also to go some steps further in my 3D printer & firmware development.

Why should you update your artillery firmware?

  - Input shaping
  - Save to EEPROM
  - P.I.D. Autotune option for hotend – also added  tuned PID settings for hotend and heatbed.
  - Manual Bed leveling
  - Linear Advance 1.5 enabled and configured K Factor to 0.13
  - S Curve Acceleration and Adaptive Step Smoothing is enabled
  - Added preheat presets for different types of materials.
  - Babystepping Z enabled
  - Quick Home enabled for faster homing
  - Changed Feedrate and Acceleration values for smooth and silent operation
  - More release notes https://github.com/MarlinFirmware/Marlin/releases/tag/2.1.2

So I went directly to https://marlinfw.org/ and learnt how to customize the latest firmware so it is perfectly fitting my 3D printer.

In order to run Marlin firmware I need also to customize and update Artillery Genius <a href="https://github.com/bigtreetech/BIGTREETECH-TouchScreenFirmware">TFT</a> firmware.

So the following files were generated for this project:

<li><a href="https://github.com/dgtaheno/artillery-Genius/blob/main/Marlin%202.0.9.3.hex">Marlin 2.1.2.hex</a></li>
<li><a href="https://github.com/dgtaheno/artillery-Genius/blob/main/SD%20TFT%20update.zip">SD TFT update.zip</a></li>

<p align="right">(<a href="#top">back to top</a>)</p>

### Built With

This is the software used to create this project:

- [Visual Studio Code](https://code.visualstudio.com/)
- [Platform.io](https://platformio.org/install/ide?install=vscode)(VS Code extension)
- [Auto Build Marlin](https://marlinfw.org/docs/basics/auto_build_marlin.html)(VS Code extension)
- [Marlin Firmware](https://marlinfw.org)
- [Big TreeTech TFT Firmware](https://github.com/bigtreetech/BIGTREETECH-TouchScreenFirmware)
- [Prusa slicer](https://www.prusa3d.com/)

<p align="right">(<a href="#top">back to top</a>)</p>

<!-- GETTING STARTED -->

## Getting Started

Please prepare your printer in a clean space, a computer and a USB cable to connect the computer to the motherboard.

### Prerequisites

<span style="color:red">Please note that to update the firmware it is necessary to open Artillery Genius 3D printer cover, which voids the warranty!!! Do it at your own risk, I will take no liability for any caused damages.</span>

Or if you already installed the TFT firmware it is so much easier.

## If you have not yet installed TFT firmware:

  Remove the bottom cover.

  The cable between TFT touchscreen and the motherboard needs to be removed in order to get a connection from the computer and flash the board firmware, it is usually glued, I found super helpful using a hair dryer to melt the glue, so it the connector comes out easy.

  With the firmware flashed, you can now connect the TFT cable back to its original position and put the bottom cover back.
## If you have already updated the TFT firmware:

  You can just open the serial connection via:

  Menu->Settings->Connection->ON

  Upload the new firmware click on OFF and restart the printer.

### Installation

First, you need to flash the board firmware. I am using Prusa Slicer to flash.

  1. Download the [Marlin 2.0.9.3.hex](https://github.com/dgtaheno/artillery-Genius/blob/main/Marlin%202.0.9.3.hex) for Artillery Genius firmware
  2. Open Prusa Slicer
  3. Go to Configuration -> Flash printer firmware
  4. Select the Marlin 2.0.9.3.hex file provided, and choose the correct serial port for your printer.
  5. Click Flash! and wait for the process to finish.

  After flashing the firmware, make sure you first run the [G-Code](https://github.com/dgtaheno/artillery-Genius/blob/main/Reset%20Settings.gcode) provided, to reset to factory defaults and clear EEPROM. Copy the .gcode file on your SD Card and “print” it.
  You can also run the following commands in sequence:

  M502
  M500
  M501

Second you need to update TFT firmware:

  1. Download [TFT Firmware](https://github.com/dgtaheno/artillery-Genius/blob/main/SD%20TFT%20update.zip) for Artillery Genius
  2. Copy the contents of [TFT Firmware](https://github.com/dgtaheno/artillery-Genius/blob/main/SD%20TFT%20update.zip) for Artillery Genius folder in the root of the SD Card
  3. Plug your SD Card in your printer
  4. Start the printer and wait for the flashing process to finish.

  The printer will reboot when finished.

You can close again the bottom cover and start having fun.

In case of issues, you can always download original firmware from https://www.artillery3d.com/pages/downloads

<p align="right">(<a href="#top">back to top</a>)</p>

<!-- USAGE EXAMPLES -->

## Usage

I recommend you start working with this new firmwares following some calibrations:

https://3dprintbeginner.com/3d-printer-calibration/

And start working with it to become familiar with all functionalities.

If you don´t know how to do calibrate Input Shaping, I found this description in MarlinFW quite useful:

https://marlinfw.org/docs/gcode/M593.html

Also in this Youtube video you can find plenty useful info:

https://www.youtube.com/watch?v=7VLuz3hReYw


<p align="right">(<a href="#top">back to top</a>)</p>

<!-- ROADMAP -->

## Roadmap

- [x] Create initial README.md
- [x] Customize and compile Marlin 2.0.9.3 firmware for Artillery Genius 3D printer.
- [x] Customize and compile TFT firmware.
- [x] Add GNU License.
- [x] Add updated REDAME.md
  - [x]Add logo.png
  - [x]Add Reset Settings.gcode

See the [open issues](https://github.com/dgtaheno/artillery-Genius/issues) for a full list of proposed features (and known issues).

<p align="right">(<a href="#top">back to top</a>)</p>

<!-- CONTRIBUTING -->

## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<p align="right">(<a href="#top">back to top</a>)</p>

<!-- LICENSE -->

## License

Distributed under the GNU License. See `LICENSE` for more information.

<p align="right">(<a href="#top">back to top</a>)</p>

<!-- CONTACT -->

## Contact

David García-Taheno Fernández -  dgtaheno@hotmail.com

Project Link: [https://github.com/dgtaheno/artillery-Genius](https://github.com/dgtaheno/artillery-Genius)

<p align="right">(<a href="#top">back to top</a>)</p>

<!-- ACKNOWLEDGMENTS -->

## Acknowledgments

Resources I found helpful and would like to give credit to.

- [Best README.md template](https://github.com/othneildrew/Best-README-Template)
- [3D print beginner](https://3dprintbeginner.com/artillery-genius-firmware/)
- [Marlin Firmware](https://marlinfw.org/)
- [Big treetech](https://github.com/bigtreetech/BIGTREETECH-TouchScreenFirmware)

<p align="right">(<a href="#top">back to top</a>)</p>

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[contributors-shield]: https://img.shields.io/github/contributors/dgtaheno/artillery-Genius.svg?style=for-the-badge
[contributors-url]: https://github.com/dgtaheno/artillery-Genius/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/dgtaheno/artillery-Genius.svg?style=for-the-badge
[forks-url]: https://github.com/dgtaheno/artillery-Genius/network/members
[stars-shield]: https://img.shields.io/github/stars/dgtaheno/artillery-Genius.svg?style=for-the-badge
[stars-url]: https://github.com/dgtaheno/artillery-Genius/stargazers
[issues-shield]: https://img.shields.io/github/issues/dgtaheno/artillery-Genius.svg?style=for-the-badge
[issues-url]: https://github.com/dgtaheno/artillery-Genius/issues
[license-shield]: https://img.shields.io/github/license/dgtaheno/artillery-Genius.svg?style=for-the-badge
[license-url]: https://github.com/dgtaheno/artillery-Genius/blob/main/LICENSE
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/dgtaheno/?locale=en_US
[product-screenshot]: logo.png
