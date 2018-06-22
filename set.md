tensorflow1.8.0にアップデートした際の注意点

まずtensorflow-gpuをver1.8.0にアップデートしてみる
$sudo pip3 install --upgrade tensorflow-gpu

こんなエラーが出てくる
ImportError: libcublas.so.9.0: cannot open shared object file: No such file or directory

どうやらcudaのバージョンが問題らしい
->cudaをアップデートしてみた

cuda9.0をインストール
$sudo apt install cuda-9-0

https://developer.nvidia.com/rdp/cudnn-download から
cuDNN 7.1.4 for CUDA 9.0中の
cuDNN v7.1.4 Runtime Library for Ubuntu16.04 (Deb)
cuDNN v7.1.4 Developer Library for Ubuntu16.04 (Deb)
cuDNN v7.1.4 Code Samples and User Guide for Ubuntu16.04 (Deb)
をダウンロード

その後
sudo dpkg -i libcudnn7_7.1.4.18-1+cuda9.0_amd64.deb
sudo dpkg -i libcudnn7-dev_7.1.4.18-1+cuda9.0_amd64.deb
sudo dpkg -i libcudnn7-doc_7.1.4.18-1+cuda9.0_amd64.deb
を実行する。


tensorflow-gpu 1.8.0が使用可能になった。



