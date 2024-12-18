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
    INSTALL_PATH=/opt/alist
    SERVICE_PATH=/etc/systemd/system

    mkdir -p $pkgdir$INSTALL_PATH
    tar -xf ./alist-${pkgver}-linux-amd64.tar.gz -C $pkgdir$INSTALL_PATH

    mkdir -p $pkgdir$SERVICE_PATH
    cat > $pkgdir$SERVICE_PATH/alist.service << EOF
[Unit]
Description=Alist service
Wants=network.target
After=network.target network.service

[Service]
Type=simple
WorkingDirectory=$INSTALL_PATH
ExecStart=$INSTALL_PATH/alist server
KillMode=process

[Install]
WantedBy=multi-user.target
EOF

}
