# Kivy_Tutorial

## まえがき

環境は、Minicondaを想定。上手いこと、インストールして下さい。

もしかすると、どこか間違ってるかもしれないので、その辺りはご了承ください。

## Kivyのインストール(Windows)

Pythonのバージョンは、< 3.5を推奨。

とりあえず、仮想環境を作って、Python 3.4.5をインストール。

- 仮想環境の作成

  `conda create -n kivy python=3.4.5`

環境を作った後、pip wheelのアップデートをする。

- pip, wheelのアップデート

  `python -m  pip install --upgrade pip wheel setuptools`

Kivyのインストールには、Cythonが必要とのことなので、インストールする。

- Cythonのインストール

  `pip install Cython`

後は、[公式の説明](https://kivy.org/docs/installation/installation-windows.html)に従って、下記の通りに必要なパッケージをインストールする。

- Kivyのインストール

  `pip install docutils pygments pypiwin32 kivy.deps.sdl2 kivy.deps.glew`

  `pip install kivy`

後は、Pythonを起動して、Kivyがインポートできるかを確認。

- 動作確認

  `import kivy`で、エラーが出なければ、OK。

## Kivyのインストール(Mac)

Homebrewを使って、以下のパッケージをインストール。[ここ](https://kivy.org/docs/installation/installation-osx.html)のサイトを参考。

- 事前準備(Homebrew)

  `$ brew install pkg-conig sdl2 sdl2_image sdl2_ttf sdl2_mixer gstreamer`

Cythonのインストールまでは、Windowsと一緒。なぜか、バージョンを0.26.1としている。

- Cythonのインストール

  `pip install -I Cython==0.26.1`

この後、pipからインストールするが、PyPIではなくgitから持ってこないと駄目。

PyPIからインストールすると、なぜかエラーを吐く。

- Kivyのインストール(Mac)

  `USE_OSX_FRAMEWORKS=0 pip install git+https://github.com/kivy/kivy.git`

こうやってインストールすると、cloneする必要がないとのこと。

インストール後は、Windowsと同じようにインポートできるかを確認。

## Hello Worldのソースコード

とりあえず、載せときます。

```Python
import kivy
from kivy.app import App
from kivy.uix.label import Label

class HelloApp(App):

    def build(self):
        return Label(text='Hello World')

if __name__ == '__main__':
    HelloApp().run()
```

## Kivyチュートリアル

[公式サイト](https://kivy.org/docs/tutorials/pong.html#)で解説されてる通りに、コードを作成した。

srcを参照のこと。

### コード一覧
- hello.py

  Kivy用Hello World

- pong.py, pong.kv

  Pong Game Tutorial

- paint_app.py

  A Simple Paint App
