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
- **Python 3.10**
- **pip**:
  + **Phiên bản 19.0 trở lên** cho Windows.
- Windows Native Yêu cầu **Microsoft Visual C++ Redistributable cho Visual Studio 2015, 2017 và 2019**.
- Phần mềm NVIDIA® sau đây chỉ được yêu cầu để hỗ trợ GPU.
  + Trình điều khiển GPU **NVIDIA® >= 528,33** cho WSL trên Windows.

# Hướng dẫn cài đặt
**1. Yêu cầu hệ thống**
Windows 7 trở lên (64-bit)
**2. Cài đặt Microsoft Visual C++ Redistributable**
- [Tải xuống Microsoft Visual C++](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads)
- Kéo xuống và chọn để tải về

![image](https://github.com/user-attachments/assets/bd878fd7-893a-457a-a716-5ed3f14f74c9)

* Đảm bảo [đường dẫn dài được bật](https://superuser.com/questions/1119883/windows-10-enable-ntfs-long-paths-policy-option-missing) trên Windows.
3. Cài đặt Miniconda
