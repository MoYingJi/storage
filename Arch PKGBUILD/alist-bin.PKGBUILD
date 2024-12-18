# Maintainer: MoYingJi <moyingjiaw@outlook.com>
pkgname=alist-bin
pkgdesc="一个支持多存储的文件列表/WebDAV程序"
pkgver=$(curl -s https://api.github.com/repos/AlistGo/alist/releases/latest | jq -r '.tag_name | gsub("^v"; "")')
pkgrel=1
arch=("x86_64")
url="https://alist.nn.ci/"
license=("AGPL-3.0-only")
depends=()
provides=("alist")
conflicts=("alist")
source=("alist-${pkgver}-linux-amd64.tar.gz::https://github.com/AlistGo/alist/releases/download/v${pkgver}/alist-linux-musl-amd64.tar.gz")
sha256sums=('SKIP')

package() {
    dir=$pkgdir/opt/alist
    mkdir -p $dir
    tar -xf ./alist-3.41.0-linux-amd64.tar.gz -C $dir
}
