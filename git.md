## git の使い方

git は有名なバージョン管理ツールです。
git を使うと、誰がいつどの行を（どういう意図で）更新したかなどを簡単に把握することができます。
おそらくあらゆる開発現場で使われているので、研究生活中に慣れておいて損はないと思います。

これは git にあまり慣れていない人を対象としたドキュメントですが、ある程度gitに慣れている人にも[おすすめのツール](#おすすめのツール)は役立つかもしれません。

## とりあえずGitHubにpushしたい

不慣れなうちは、以下のコマンドを打てばとりあえずは問題ないです：

```sh
git add *
git commit -m "Update"
git push
# input your username and password
```

## おすすめのツール

以下では、 git にまつわる作業をラクにしてくれるツールを紹介します。

### ghq

[ghq](https://github.com/x-motemen/ghq) を使うと、リモートからクローンしてきたリポジトリを一元管理することができます。
具体的には、今までなら「クローンしたいディレクトリを `mkdir` し、そこへ `cd` し、そして `git clone <repo>` ・・・」としていた手順を、 `ghq get <repo>` という1コマンドで完了させることができます。

例えば本リポジトリ (https://github.com/fseclab-osaka/tips_pub) に対し `ghq get` すると、 `$HOME/ghq/github.com/tips_pub` 下にクローンされます。
なお、 必ずしも github.com に存在するリポジトリである必要は無く、例えば gitlab.com にあるものでも git.savannah.gnu.org にあるものでも正常にクローンしてくれます。

インストール方法は以下です (go のバージョンは 2024/03/13 時点のもの)：

```sh
# install go (https://go.dev/doc/install)
curl -LO https://go.dev/dl/go1.22.1.linux-amd64.tar.gz
sudo rm -rf /usr/local/go && sudo tar -C /usr/local -xzf go1.22.1.linux-amd64.tar.gz
export PATH=$PATH:/usr/local/go/bin

# install ghq (https://github.com/x-motemen/ghq?tab=readme-ov-file#go-get)
go install github.com/x-motemen/ghq@latest
```

