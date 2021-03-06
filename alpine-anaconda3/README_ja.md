# alpine-anaconda3 / Dockerfile

この Dockerfile は、Alpine Linux 上に [Anaconda3](https://www.continuum.io/) を使って Python 環境を構築します。

Jupyter Notebook での利用を前提とした作りになっています。また、IRuby も使えるようにしています。IRuby 関連では、以下のパッケージを同梱しています。

* pry
* pry-doc
* awesome_print
* gnuplot
* rubyvis
* nyaplot

## Requirements

* [Docker](https://www.docker.com) 1.12.1+

## Usage

Docker イメージを作るには、次のコマンドを使用します。

```text
docker build -t my-anaconda3 .
```

以下のコマンドは、Jupyter Notebook の起動例です。

```text
docker run -it --rm -v $(pwd):/opt/notebooks -p 8888:8888 my-anaconda3 jupyter notebook --notebook-dir=/opt/notebooks --ip="0.0.0.0" --port=8888 --no-browser
```

Jupyter Notebook が起動すると、以下のようなメッセージが表示されます。

```text
The Jupyter Notebook is running at: http://0.0.0.0:8888/?token=************************************************
```

このメッセージで示された `http://0.0.0.0:8888/?token=************************************************` をウェブブラウザーでオープンします。

## License

This is licensed under the [MIT](https://github.com/asakaguchi/dockerfiles/blob/master/LICENSE) license.