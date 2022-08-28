<div id="top"></div>
<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Don't forget to give the project a star!
*** Thanks again! Now go create something AMAZING! :D
-->



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
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]


<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/VarCode-ai/yolox-face-detection">
    <img src="logo.png" alt="Logo" width="80" height="80">
  </a>

<h3 align="center">Yolox Face Detection</h3>

  <p align="center">
    How to train and use Yolox on WiderFace dataset
    <br />
    <a href="https://github.com/VarCode-ai/yolox-face-detection/blob/main/Yolox_train_WiderFace.ipynb"><strong> View Jupyter Notebook »</strong></a>
    <br />
    <br />
    <a href="https://github.com/VarCode-ai/yolox-face-detection/tree/main/YOLOX_outputs/yolox_voc_s">View Test</a>
    ·
    <a href="https://github.com/VarCode-ai/yolox-face-detection/issues">Report Bug</a>
    ·
    <a href="https://github.com/VarCode-ai/yolox-face-detection/issues">Request Feature</a>
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


YOLOX is an anchor-free version of YOLO with strong performance for object detection. In this repository I train Yolox on WiderFace dataset with Google Colab to develop a face detection algorithm.
<p align="right">(<a href="#top">back to top</a>)</p>


### Built With

* [Yolox](https://github.com/Megvii-BaseDetection/YOLOX)
* [Wider Face Dataset](http://shuoyang1213.me/WIDERFACE/)

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- GETTING STARTED -->
## Getting Started

Look at Jupyter Notebooks to see training details and how to make this algorithm from scratch.  

### Installation

1. Clone the repo
   ```sh
   git clone https://github.com/VarCode-ai/yolox-face-detection.git
   cd yolox-face-detection
   ```

2. Install YOLOX
   ```sh
   pip3 install -U pip && pip3 install -r requirements.txt

   pip3 install -v -e .

   pip3 install "git+https://github.com/philferriere/cocoapi.git#egg=pycocotools&subdirectory=PythonAPI"

   pip3 install cython
   ```

3. Download JPEGImages of Wider Face dataset
   ```sh
   cd datasets\VOCdevkit\VOC2022\JPEGImages
   python download_images.py
   ```

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- USAGE EXAMPLES -->
## Usage
### Real time detection
```sh
python tools/demo.py webcam -f exps/example/yolox_voc/yolox_voc_s.py -c YOLOX_outputs/yolox_voc_s/latest_ckpt.pth --conf 0.25 --nms 0.45 --tsize 640 --device [cpu/gpu]
```
### Images
```sh
python tools/demo.py image -f exps/example/yolox_voc/yolox_voc_s.py -c YOLOX_outputs/yolox_voc_s/latest_ckpt.pth --path assets/001.jpg --conf 0.25 --nms 0.45 --tsize 640 --save_result --device [cpu/gpu]
```

### Video
```sh
python tools/demo.py video -f exps/example/yolox_voc/yolox_voc_s.py -c YOLOX_outputs/yolox_voc_s/latest_ckpt.pth --path assets/will_smith_slap.mp4 --conf 0.25 --nms 0.45 --tsize 640 --save_result --device [cpu/gpu]
```


_For more examples, please refer to the [Documentation](https://yolox.readthedocs.io/en/latest/)_

<p align="right">(<a href="#top">back to top</a>)</p>

### Train from pre-trained weights
[Weights trained for 6 epochs](https://github.com/VarCode-ai/yolox-face-detection/blob/main/YOLOX_outputs/yolox_voc_s/latest_ckpt.pth)

Code for resume training
```sh
python tools/train.py -f exps/example/yolox_voc/yolox_voc_s.py -d 1 -b 4 -c YOLOX_outputs/yolox_voc_s/latest_ckpt.pth --resume
```


<p align="right">(<a href="#top">back to top</a>)</p>


<!-- LICENSE -->
## License

Distributed under the Apache-2.0 License. See `LICENSE` for more information.

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- CONTACT -->
## Contact

Vincenzo Varriale - [@_vincenzovarriale_](https://instagram.com/_vincenzovarriale_) - vincenzo.varriale.dev@gmail.com

Project Link: [https://github.com/VarCode-ai/yolox-face-detection](https://github.com/VarCode-ai/yolox-face-detection)

<p align="right">(<a href="#top">back to top</a>)</p>







<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/VarCode-ai/yolox-face-detection.svg?style=for-the-badge
[contributors-url]: https://github.com/VarCode-ai/yolox-face-detection/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/VarCode-ai/yolox-face-detection.svg?style=for-the-badge
[forks-url]: https://github.com/VarCode-ai/yolox-face-detection/network/members
[stars-shield]: https://img.shields.io/github/stars/VarCode-ai/yolox-face-detection.svg?style=for-the-badge
[stars-url]: https://github.com/VarCode-ai/yolox-face-detection/stargazers
[issues-shield]: https://img.shields.io/github/issues/VarCode-ai/yolox-face-detection.svg?style=for-the-badge
[issues-url]: https://github.com/VarCode-ai/yolox-face-detection/issues
[license-shield]: https://img.shields.io/github/license/VarCode-ai/yolox-face-detection.svg?style=for-the-badge
[license-url]: https://github.com/VarCode-ai/yolox-face-detection/blob/master/LICENSE
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/vincenzo-varriale-83b18423a/
[product-screenshot]: images/screenshot.png
