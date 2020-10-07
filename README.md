<img src="https://github.com/Lovepreet-Singh-LPSK/Face-Recognition/blob/master/pics/FaceRecLogo.png" width="100" height="100">
<h1>Face Recognition Using Viola Jones and Eigen Faces Algorithm</h1>

This project is implemented using `Jupyter Notebook (.ipynb File)` and `Python`.


## Index

- [Demo](https://github.com/Lovepreet-Singh-LPSK/Face-Recognition#project-theory)
- [Screenshots](https://github.com/tasdikrahman/spaceShooter#screenshots)
- [Game Features](https://github.com/tasdikrahman/spaceShooter#game-features)
- [Controls](https://github.com/tasdikrahman/spaceShooter#controls)
- [Installation](https://github.com/tasdikrahman/spaceShooter#installation)
- [For Windows](https://github.com/tasdikrahman/spaceShooter#for-windows)
- [Linux/Debian based systems](https://github.com/tasdikrahman/spaceShooter#linuxdebian-based-systems)
- [Option 1: Download the zipped executable file](https://github.com/tasdikrahman/spaceShooter#option-1-download-the-zipped-executable-file)
    - [Option 2: Build from source](https://github.com/tasdikrahman/spaceShooter#option-2-build-from-source)
  - [For MAC OS X](https://github.com/tasdikrahman/spaceShooter#for-mac-os-x)
- [Contributing](https://github.com/tasdikrahman/spaceShooter#contributing)
  - [Contributers](https://github.com/tasdikrahman/spaceShooter#contributers)
  - [To-do](https://github.com/tasdikrahman/spaceShooter#to-do)
- [Issues](https://github.com/tasdikrahman/spaceShooter#issues)
- [Credits](https://github.com/tasdikrahman/spaceShooter#credits)
- [Similar](https://github.com/tasdikrahman/spaceShooter#similar)
- [License](https://github.com/tasdikrahman/spaceShooter#license)
- [Donation](https://github.com/tasdikrahman/spaceShooter#donation)

## Project Theory

[[Back to top]](https://github.com/Lovepreet-Singh-LPSK/Face-Recognition#index)

##### Introduction
Face Recognition is a process of face detection and then classifying the faces into different classes. The methods used in this case are based on the application of Viola-Jones, for detecting the face using cascade classifier, and Eigen Faces algorithm, for face classification and it is based on the PCA algorithm. PCA is known as Principal component analysis which in other words is feature reduction or dimensionality reduction algorithm.

##### The very basic flow of the Face Recognition:
![](https://github.com/Lovepreet-Singh-LPSK/Face-Recognition/blob/master/pics/flowchart.png)
- How the Viola-Jones algorithm detects Faces:→ Viola-Jones algorithm works for frontal face recognition rather than faces looking sideways. It detects the face location on the grayscale image first then it detects on the colored one. A sliding box is used to trace all the image and Haar features are obtained for each region.
- Haar-Like Features:→ ​ These are the features named Edge, Line, and four-sided features.
![](https://github.com/Lovepreet-Singh-LPSK/Face-Recognition/blob/master/pics/haarlike.png)
These features help the machine to understand the features of the image. For.ex. The edge feature has a one-sided dark and the other is light, This filter is, therefore, good at edge detection like the nose, lips line, etc. To obtain the feature value these features are placed over the region in the sliding rectangle and the sum in the light region is subtracted from the sum of pixels in the dark region.
- Haar-Like Features application:→
| ![Screen 1](https://github.com/Lovepreet-Singh-LPSK/Face-Recognition/blob/master/pics/haar-app.png) | ![Screen 2](https://github.com/Lovepreet-Singh-LPSK/Face-Recognition/blob/master/pics/haar-app.png) |
- Integral Image:→
![](https://github.com/Lovepreet-Singh-LPSK/Face-Recognition/blob/master/pics/ii.png)
​Integral image is used to obtain the values of Haar-like feature values because otherwise, it is computationally very expensive to calculate it, because of the large number of image pixels.
- Training:→
The algorithm in training is setting a minimum threshold to determine whether something can be classified as a feature or not. The computation can be really expensive depending on the different possible combinations of features for each region of the sliding rectangle.
![](https://github.com/Lovepreet-Singh-LPSK/Face-Recognition/blob/master/pics/cascade.png)
For each region, a linear combination of the weak classifiers(on the right) is obtained toform a strong classifier(on the left). AdaBoost is used forthis task. Adaboost works like,first we classify images using important feature acc. to us. The images for whichclassification is the wrong Adaboost uses another feature to classify wrong classified images, giving more importance to the wrong classified images. In other words, increasing the weight for these images in the overall algorithm. Similarly, we will go for the next feature and at last giving larger weight to the last image. Thus Adaboost forms the classifier from these Weak classifiers.
- Cascading:→
​It is a hack to increase the speed and accuracy of Boosting. 
![](https://github.com/Lovepreet-Singh-LPSK/Face-Recognition/blob/master/pics/cascade-window.png)
The feature is looked in the sub-window on the image and if Feature-i (Fi) is not present in this window then that sub-window is rejected and the process stopped for that window thus preventing further checking of the features. Since we have to do it for each feature it may be slow without Cascading.

##### How the Eigen-Faces algorithm classifies the Faces ​ (All images are obtained from my code of Facial Recognition*)​ :
- Training:→
- 1.) ​ Suppose we have M images of dimensions NxN.
| ![Screen 1](https://github.com/Lovepreet-Singh-LPSK/Face-Recognition/blob/master/pics/faces1.png) | ![Screen 2](https://github.com/Lovepreet-Singh-LPSK/Face-Recognition/blob/master/pics/faces2.png) |


## Screenshots

[[Back to top]](https://github.com/tasdikrahman/spaceShooter#index)

| ![Screen 1](http://i.imgur.com/3MzfmbT.jpg) | ![Screen 2](http://i.imgur.com/4OgIByR.png) |
|---------------------------------------------|---------------------------------------------|
| ![Screen 3](http://i.imgur.com/PFQJjE8.png) | ![Screen 4](http://i.imgur.com/lV4aIur.png) |

## Game Features

[[Back to top]](https://github.com/tasdikrahman/spaceShooter#index)

- Health bar for the space ship
- Score board to show how you are faring so far
- Power ups like
  - shield: increases the space ships life
  - bolt: increases the shooting capability of the ship by firing 2 to 3 bullets instead of one at time.
- Custom sounds and sprite animation for things like
  - meteorite explosion
  - bullet shoots
  - player explosion
- 3 lives per game
- Fun to play :)

## Controls

[[Back to top]](https://github.com/tasdikrahman/spaceShooter#index)

|              | Button              |
|--------------|---------------------|
| Move Left    | <kbd>left</kbd>     |
| Move right   | <kbd>right</kbd>    |
| Fire bullets | <kbd>spacebar</kbd> |
| Quit game    | <kbd>Esc</kbd>      |

## Installation

[[Back to top]](https://github.com/tasdikrahman/spaceShooter#index)

### For `Windows`

- :arrow_down: [Download the prebuilt zip file and unzip it.](https://github.com/tasdikrahman/spaceShooter/releases/latest)
- Run the executable named `spaceShooter` inside the extracted file.

### `Linux/Debian` based systems

#### Option 1: Download the zipped executable file

- :arrow_down: [Download the latest zip file for linux](https://github.com/tasdikrahman/spaceShooter/releases/latest)
- Unzip the file

If your download was saved on the `~/Downloads` folder

Press <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>T</kbd> to open the shell if you are on `GNU/Linux` based systems and type

```bash
$ unzip ~/Downloads/SpaceShooter-0.0.3.Linux.zip -d ~/Desktop
$ cd ~/Desktop
$ ## navigate to the unzipped file and change the file permissions for the executable
~/Desktop $ chmod +x spaceShooter
~/Desktop $ ./spaceShooter
```

This will unzip the file on your `Desktop`, you can replace it with the directory of your choice

**NOTE** : If it gives you an error, you probably don't have `unzip` installed in your system.

```bash
$ sudo apt-get install unzip
```
That should fix the error.

- Run the executable named `spaceShooter`

A Similar process would be followed for `OS X`

#### Option 2: Build from source

You need to have `pygame` installed for this option. 

### For `FreeBSD`

```sh
$ sudo pkg install devel/py-game
```

##### Clone the repo
```sh
$ git clone https://github.com/tasdikrahman/spaceShooter.git
$ cd spaceShooter/
$ chmod +x spaceShooter.py
$ python spaceShooter.py
```


### For `Ubuntu/Debian`

```bash
$ sudo apt-get install python-pygame
```

##### Clone the repo

```bash
$ git clone https://github.com/tasdikrahman/spaceShooter.git
$ cd spaceShooter/ 
$ python spaceShooter.py
```

### For `MAC OS X` 

You have to build from source to get it up and running on `OS X`. Reason?
I don't have an `OS X` system to build the executable! So I would love for a Pull request on that one.

Building from source will do the trick though


```bash
$ pip3 install hg+http://bitbucket.org/pygame/pygame
```

Install Pygame specific dependencies

```bash
$ brew install sdl sdl_image sdl_ttf portmidi libogg libvorbis
$ brew install sdl_mixer --with-libvorbis
```

##### Clone the repo

```bash
$ git clone https://github.com/tasdikrahman/spaceShooter.git
$ cd spaceShooter/ 
$ python spaceShooter.py
```

## Contributing

[[Back to top]](https://github.com/tasdikrahman/spaceShooter#index)

This game was written in one day, so the coding standards might not be up the mark. Don't be shy to make a Pull request :)

For details, please refer [the Contributing page](https://github.com/tasdikrahman/spaceShooter/blob/master/CONTRIBUTING.rst)

### Contributers

[[Back to top]](https://github.com/tasdikrahman/spaceShooter#index)

- [@bardlean86](https://github.com/bardlean86/) for adding the third missile powerup and the main menu

### To-do

[[Back to top]](https://github.com/tasdikrahman/spaceShooter#index)

- [x] Add the `windows` executable file
- [x] Add main menu for the game
- [x] Fix [bug](https://github.com/tasdikrahman/spaceShooter/blob/master/spaceShooter.py#L372) which stops the background music from looping 
- [x] Add support for `WAV` game music file as `ogg` format is not playable as described in [#1](https://github.com/tasdikrahman/spaceShooter/issues/1)
- [ ] Add feature to pause to the game.
- [ ] add feature to replay the game after all players die
- [ ] Add `OS X` executable file as the `Debian` based one fails to execute on it


## Issues

[[Back to top]](https://github.com/tasdikrahman/spaceShooter#index)

You can report the bugs at the [issue tracker](https://github.com/tasdikrahman/spaceShooter/issues)

**OR**

You can [tweet me](https://twitter.com/tasdikrahman) if you can't get it to work. In fact, you should tweet me anyway.

## Credits

The game is a fork of the video instructions given by KidsCanCode. I have made several additional enhancements to it. Do check out their [Channel](https://www.youtube.com/channel/UCNaPQ5uLX5iIEHUCLmfAgKg)!

## Similar

[[Back to top]](https://github.com/tasdikrahman/spaceShooter#index)

- [Bullethell.py ](https://github.com/Frederikxyz/bullethell.py) : A fork of [tasdikrahman/spaceShooter](https://github.com/tasdikrahman/spaceShooter) which adds fancy shooting capabilities

## License

[[Back to top]](https://github.com/tasdikrahman/spaceShooter#index)

Built with ♥ by [Tasdik Rahman](http://tasdikrahman.me)[(@tasdikrahman)](https://twitter.com/tasdikrahman) under [MIT License](http://tasdikrahman.mit-license.org)

You can find a copy of the License at http://tasdikrahman.mit-license.org/

- The images used in the game are taken from [http://opengameart.org/](http://opengameart.org/), more particulary from the [Space shooter content pack](http://opengameart.org/content/space-shooter-redux) from [@kenney](http://opengameart.org/users/kenney).

License for them is in `Public Domain`

- The game sounds were again taken from [http://opengameart.org/](http://opengameart.org/). The game music, [Frozen Jam](http://opengameart.org/content/frozen-jam-seamless-loop) by [tgfcoder](https://twitter.com/tgfcoder) licensed under [CC-BY-3](http://creativecommons.org/licenses/by/3.0/)

## Donation

[[Back to top]](https://github.com/tasdikrahman/spaceShooter#index)

If you have found my little bits of software being of any use to you, do consider helping me pay my internet bills :)

| PayPal | <a href="https://paypal.me/tasdik" target="_blank"><img src="https://www.paypalobjects.com/webstatic/mktg/logo/AM_mc_vs_dc_ae.jpg" alt="Donate via PayPal!" title="Donate via PayPal!" /></a> |
|:-------------------------------------------:|:-------------------------------------------------------------:|
| Gratipay  | <a href="https://gratipay.com/tasdikrahman/" target="_blank"><img src="https://cdn.rawgit.com/gratipay/gratipay-badge/2.3.0/dist/gratipay.png" alt="Support via Gratipay" title="Support via Gratipay" /></a> |
| Patreon | <a href="https://www.patreon.com/tasdikrahman" target="_blank"><img src="http://i.imgur.com/ICWPFOs.png" alt="Support me on Patreon" title="Support me on Patreon" /></a> |
| £ (GBP) | <a href="https://transferwise.com/pay/d804d854-6862-4127-afdd-4687d64cbd28" target="_blank"><img src="http://i.imgur.com/ARJfowA.png" alt="Donate via TransferWise!" title="Donate via TransferWise!" /></a> |
| € Euros | <a href="https://transferwise.com/pay/64c586e3-ec99-4be8-af0b-59241f7b9b79" target="_blank"><img src="http://i.imgur.com/ARJfowA.png" alt="Donate via TransferWise!" title="Donate via TransferWise!" /></a> |
| ₹ (INR)  | <a href="https://www.instamojo.com/@tasdikrahman" target="_blank"><img src="https://www.soldermall.com/images/pic-online-payment.jpg" alt="Donate via instamojo" title="Donate via instamojo" /></a> |