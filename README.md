# kube-image-syncer Overview
## 机器人特性
1.  支持 kubernetes 指定版本镜像自动同步
2.  支持任意镜像列表自动同步

## 技术分享
- [bilibili](https://www.bilibili.com/video/BV1XM4y1773u/?spm_id_from=333.999.0.0&vd_source=25a0f959130bc36000c91cfe0e698400) B站视频教程

## 交流沟通
- 搜索微信号 swm0908kx, 备注（image）, 验证通过会加入群聊

## 一、kubernetes 指定版本镜像自动同步
### 1、修改 config.yaml
将  `push_kubernetes: false` 中的 `false` 修改为`true`，例如 `push_kubernetes: true`
<br>
将  `version: v1.23.6` 中的版本号修改为想要拉取的版本，例如 `version: v1.23.8`
### 2、创建新的分支（按照步骤操作）
<img width="1075" alt="image" src="https://github.com/kube-robot/kube-image-syncer/assets/132827062/269b74f1-3430-4573-bbd9-7f9f23f5b4aa">
<img width="748" alt="image" src="https://github.com/kube-robot/kube-image-syncer/assets/132827062/3e1237d5-1d08-4217-9ebb-29b52e5a106b">

### 3、推送pr
<img width="1398" alt="image" src="https://github.com/kube-robot/kube-image-syncer/assets/132827062/2be623d2-d45e-4494-a577-1b6684657f9b">


CI 过程（点击 `Details` 查看 CI 详细过程）
<img width="1043" alt="image" src="https://github.com/kube-robot/kube-image-syncer/assets/132827062/b3b2f2b2-b20f-4e9d-a5e4-e32aeac1bd33">

CI 过程无异常
<img width="1413" alt="image" src="https://github.com/kube-robot/kube-image-syncer/assets/132827062/6b93cbaa-d2ab-4492-8bf6-260371351f8b">

### 4、在 dockerhub 中查看刚刚推送的镜像
在 `dockerhub` 中搜索 `pixiuio` 
![image](https://user-images.githubusercontent.com/132827062/236989636-d84bd9d2-6709-4a6e-b808-7f70dd98d9de.png)
找到 `pixiuio/kube-apiserver` 进去查看刚才推送的镜像
![image](https://user-images.githubusercontent.com/132827062/236989963-8c586083-1869-40a4-9fc0-b6f6518ab729.png)
![image](https://user-images.githubusercontent.com/132827062/236990039-03d7af68-84ce-4cd8-8aec-7774cef3d5a5.png)

## 二、任意镜像列表自动同步
### 1、修改 config.yaml
将  `push_images: false` 中的 `false` 修改为`true`，例如 `push_images: true`
<br>
将想要上传的镜写在这个列表下
```yaml
  images:
    - docker.io/nginx:latest
    - docker.io/redis:latest

注意：写全域名
```
<img width="957" alt="image" src="https://github.com/kube-robot/kube-image-syncer/assets/132827062/85831d87-5c38-4b9b-834b-f56f1663373c">

查看 CI 结果，显示推送成功
<img width="1429" alt="image" src="https://github.com/kube-robot/kube-image-syncer/assets/132827062/b8d81344-05f2-4f04-8f6f-dd42a72145ce">

创建分支推送 pr 步骤和前面相同，请参照前面步骤

### 2、查看 dockerhub 查看刚刚推送结果
<img width="1379" alt="image" src="https://github.com/kube-robot/kube-image-syncer/assets/132827062/bcb2c181-1977-4718-8d65-02e8cd2f5746">





