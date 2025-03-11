# Install_Tensorflow_GPU_On_VSCode
Cài đặt Tensorflow GPU (**Windows Gốc - Windows Native**) trên VSCode.

# Thông tin chung
Cấu hình Laptop (của tôi):
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

![image](https://github.com/user-attachments/assets/78b3b55a-240b-419b-9bd0-1265ca38ba9f)

- **pip**:
  + **Phiên bản 19.0 trở lên** cho Windows.
```bash
python.exe -m pip install --upgrade pip
```

- Windows Native Yêu cầu **Microsoft Visual C++ Redistributable cho Visual Studio 2015, 2017 và 2019**.
- Phần mềm NVIDIA® sau đây chỉ được yêu cầu để hỗ trợ GPU.
  + Trình điều khiển GPU **NVIDIA® >= 528,33** cho WSL trên Windows.
 
![image](https://github.com/user-attachments/assets/784a7c01-7bb2-4426-828e-7cb9fdfb7251)

# Hướng dẫn cài đặt
**1. Yêu cầu hệ thống**

> Windows 7 trở lên (64-bit).

**2. Cài đặt Microsoft Visual C++ Redistributable**

> [Tải xuống Microsoft Visual C++](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads)

> Kéo xuống, chọn để tải về và cài đặt.

![image](https://github.com/user-attachments/assets/bd878fd7-893a-457a-a716-5ed3f14f74c9)

> Đảm bảo [đường dẫn dài được bật](https://superuser.com/questions/1119883/windows-10-enable-ntfs-long-paths-policy-option-missing) trên Windows.
- Nhấn Windows + R > Gõ "gpedit.msc"

![image](https://github.com/user-attachments/assets/cbdffe7d-ebc6-461e-a383-dccdddbb6261)

- Chọn theo đường dẫn **Computer Configuration** > **Administrative Templates** > **System** > **Filesystem** (Tùy máy sẽ nằm trong **NTFS**)

![image](https://github.com/user-attachments/assets/69dbb318-dc39-4cf0-9db5-668ca2cfb204)

 - Chọn "**Enable Win32 long paths**" và **Enabled**.

**3. Cài đặt Miniconda**
> [Tải xuống Windows Miniconda](https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe) và cài đặt.

**4. Tạo môi trường ảo**
> Liên kết đến [Cài đặt môi trường ảo trên VSCode.](https://github.com/KhanhPhQ/Install_Virtual_Environment_On_VSCode)

**5. Thiết lập GPU**
> Mở Terminal trong VSCode với môi trường ảo, chạy lệnh.
```bash
conda install -c conda-forge cudatoolkit=11.2 cudnn=8.1.0
```

![image](https://github.com/user-attachments/assets/7c2978fa-04d9-4e0c-a7e5-9a55fbba5695)

> Sau khi quá trình trên chạy xong, chạy tiếp các lệnh bên dưới.
```bash
pip install "numpy<2"
pip install "tensorflow<2.11"
pip install tensorflow-datasets
pip install matplotlib
```

**6. Kiểm tra nhận diện GPU trên Windows**
Tạo 1 File Python đuôi ".py" và nhập mã bên dưới để kiểm tra.
```bash
import tensorflow as tf

print("TensorFlow version:", tf.__version__)
gpus = tf.config.list_physical_devices('GPU')
if gpus:
    print("Số GPU khả dụng:", len(gpus))
    for gpu in gpus:
        # Lấy thông tin chi tiết của GPU
        details = tf.config.experimental.get_device_details(gpu)
        # Nếu có thông tin tên, in ra; nếu không thì in tên mặc định của đối tượng GPU
        gpu_name = details.get('device_name', gpu.name)
        print("Tên GPU:", gpu_name)
else:
    print("Không tìm thấy GPU.")
```

![image](https://github.com/user-attachments/assets/f3d7b020-5c5d-400b-aac6-08af0ebba3ba)

**=> Thành công, nhận diện GPU.**
