# Install_Tensorflow_GPU_On_VSCode
Cài đặt Tensorflow GPU (**Windows Gốc - Windows Native**) trên VSCode.

# Thông tin chung
Cấu hình Laptop:
- Dell Precision 5530
- Windows: 11 Pro 24H2
- Processor: Intel(R) Core(TM) i9-8950HK CPU @ 2.90GHz   2.90 GHz
- Installed RAM: 32,0 GB

# Cài đặt Tensorflow
Trang chủ Tensorflow: _**https://www.tensorflow.org/**_

> **Yêu cầu phần cứng**
- Xem danh sách [GPU hỗ trợ CUDA®](https://developer.nvidia.com/cuda-gpus)
- Đối với các **GPU không được hỗ trợ**, [cài đặt bằng Linux](https://www.tensorflow.org/install/source)

> **Yêu cầu hệ thống**
- Windows Native - Windows 7 trở lên (64-bit) (không hỗ trợ GPU sau TF 2.10)

> **Yêu cầu phần mềm**
- Python 3.9 - 3.12
- pip:
  + Phiên bản 19.0 trở lên cho Linux và Windows.
  + Phiên bản 20.3 trở lên cho macOS.
- Windows Native Yêu cầu [Microsoft Visual C++ Redistributable cho Visual Studio 2015, 2017 và 2019](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads)
- Phần mềm NVIDIA® sau đây chỉ được yêu cầu để hỗ trợ GPU. Trình điều khiển GPU NVIDIA®
  + >= 525.60.13 cho Linux
  + >= 528,33 cho WSL trên Windows
