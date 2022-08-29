LEAN_ID 和 LEAN_KEY 分别对应的是后台得到的 App Id 和 App Key。如果非 LeanCloud 国际版用户的话需要在后台绑定已备案域名并配置 LEAN_SERVER。

如何构建镜像？
```
git clone https://github.com/walinejs/waline.git
cd waline
docker build -t lizheming/waline -f packages/server/Dockerfile .
```