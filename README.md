# kube-image-syncer
## 1、修改 .github/workflows/sync-image.yaml 文件
将  `version: v1.23.6` 中的版本号修改为想要拉取的版本，例如 `version: v1.23.8` 
将  `push_kubernetes: false` 中的 `false` 修改为`true`，例如 `push_kubernetes: true`
## 2、创建新的分支（按照步骤操作）
![image](https://user-images.githubusercontent.com/132827062/236986745-8cc7ce86-a995-4db9-8ca4-add4707374f1.png)
![image](https://user-images.githubusercontent.com/132827062/236986958-441a2f4b-b631-4786-99d9-f1f72a647533.png)
推送pr
![image](https://user-images.githubusercontent.com/132827062/236988576-d141621d-8f82-42a1-b271-20099bdef446.png)
CI 过程（点击 `Details` 查看 CI 详细过程）
![image](https://user-images.githubusercontent.com/132827062/236990461-5c15d6b9-be26-40f7-b8e8-20ab0540f6c0.png)
CI 过程无异常
![image](https://user-images.githubusercontent.com/132827062/236988927-7b4a302d-5a5f-4d3b-8159-4f180aeef0bd.png)
## 3、在dockerhub中查看刚刚推送的镜像
在 `dockerhub` 中搜索 `pixiuio` 
![image](https://user-images.githubusercontent.com/132827062/236989636-d84bd9d2-6709-4a6e-b808-7f70dd98d9de.png)
找到 `pixiuio/kube-apiserver` 进去查看刚才推送的镜像
![image](https://user-images.githubusercontent.com/132827062/236989963-8c586083-1869-40a4-9fc0-b6f6518ab729.png)
![image](https://user-images.githubusercontent.com/132827062/236990039-03d7af68-84ce-4cd8-8aec-7774cef3d5a5.png)





