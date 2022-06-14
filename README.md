# CS331.M22-KHCL  
<h1 align="center">Thị giác máy tính nâng cao</h1>
 
<!-- PROJECT LOGO -->
<div align="center">
  <h3 align="center">COURSE PROJECT</h3>
  <a>
    <img src="https://www.cio.com/wp-content/uploads/2021/12/ai-in-automotive_1280x609-100790232-orig.jpeg?quality=50&strip=all" alt="Logo" width="640" height="304.5">
  </a>

  <h3 align="center">AN IN-CAR CAMERA SYSTEM FOR TRAFFIC SIGN DETECTION AND RECOGNITION</h3>

  <p align="center">
    USING RETINA NET, FASTERCNN, YOLOv5
    <br />
    <br />
    <a href="https://www.miai.vn/2021/04/01/xay-dung-he-thong-nhan-dien-bien-bao-giao-thong-bang-retinanet/">RETINA NET</a>
    ·
    <a href="https://viblo.asia/p/deep-learning-thuat-toan-faster-rcnn-voi-bai-toan-phat-hien-duong-luoi-bo-faster-rcnn-object-detection-algorithm-for-nine-dash-line-detection-bJzKmREOZ9N">FASTERRCNN</a>
    ·
    <a href="https://viblo.asia/p/tong-hop-kien-thuc-tu-yolov1-den-yolov5-phan-1-naQZRRj0Zvx">YOLOv5</a></br>
    <a href="https://drive.google.com/drive/folders/1WT62tiCCsOyEOoRtkzo4n9BwpufK0zmb">LINK PROJECT</a>
  </p>
</div>


<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#Tổng-quan">Tổng quan</a>
    </li>
    <li>
      <a href="#Mô-tả-bài-toán">Mô tả bài toán</a>
      <ul>
        <li><a href="#Input">Input</a></li>
        <li><a href="#Output">Output</a></li>
      </ul>
    </li>
    <li><a href="#usage">Khái quát bộ dữ liệu</a></li>
    <li><a href="#roadmap">Xây dựng bộ dữ liệu</a>
      <ul>
         <li><a href="#built-with">Các tiêu chí đề ra</a>
      </ul>
      <ul>
         <li><a href="#built-with">Label sử dụng LabelImg</a>
      </ul>
      <ul>
         <li><a href="#built-with">Phân bố lớp trong bộ dữ liệu</a>
      </ul>
    </li>
    <li><a href="#contributing">Hướng tiếp cận</a></li>
      <ul>
         <li><a href="#built-with">Giới thiệu về Retina Net</a>
      </ul>
      <ul>
         <li><a href="#built-with">Giới thiệu về FasterRCNN</a>
      </ul>
      <ul>
         <li><a href="#built-with">Giới thiệu về YOLOv5</a>
      </ul>
    <li><a href="#license">Training và Đánh giá model</a></li>
    <li><a href="#contact">So sánh</a></li>
  </ol>
</details>

<!-- TỔNG QUAN -->
## Tổng quan

<div align="center">
 <a>
    <img src="https://storage.googleapis.com/enterknow.com/data-contents/2021/09/autonomous-driving.jpg" alt="Logo" width="600" height="375">
 </a>
</div>
 
Trong thời đại ngày càng phát triển, việc giúp cho máy tính có thể nhận diện các đối tượng giống như con người ngày càng trở nên quan trọng. Và nhóm chúng em đã nghiên cứu để giúp máy tính có thể nhận diện được biển báo giao thông ứng dụng trong phát triển xe tự hành. Qua đó có thể giúp xe tự hành có thể tự lưu thông trên đường 1 cách an toàn hơn mà không gây ảnh hưởng đến người lái xe cũng như những người tham gia giao thông trên cùng tuyến đường.

<p align="right">(<a href="#top">back to top</a>)</p>

<!-- MÔ TẢ BÀI TOÁN -->
## Mô tả bài toán
### Input
Một hình ảnh chứa biển báo giao thông dưới góc nhìn của camera hành trình ô tô.

### Output
Hình ảnh chứa bounding box các loại biển báo giao thông và nhãn cho các bounding box đó.

Detect 5 loại biển chính:
* Cấm đi ngược chiều.
* Hướng đi phải vòng sang phải.
* Giao nhau với đường không ưu tiên.
* Cấm đỗ xe.
* Người đi bộ.

<div align="center">
 <a>
    <img src="https://thietbigiaothong247.com/wp-content/uploads/2017/04/bien-cam-di-nguoc-chieu-400x400.jpg" alt="Logo" width="100" height="100">
 </a>
 <a>
    <img src="http://www.baoholaodong247.com/Portals/26918/302a.jpg" alt="Logo" width="100" height="100">
 </a>
 <a>
    <img src="https://alohoc.com/data/upload/2019/0217/207c-giao-nhau-voi-duong-khong-uu-tien-500x500.jpg?ver=1655170526" alt="Logo" width="100" height="100">
 </a>
 <a>
    <img src="https://thuthuat.taimienphi.vn/cf/Images/gl/2019/4/5/bien-bao-cam-do-xe-p-131a-p-131b-p-131c.jpg" alt="Logo" width="100" height="100">
 </a>
 <a>
    <img src="http://baoholaodong247.com/DesktopModules/Store/Thumbnail.aspx?IP=/Portals/26918/423b.jpg&IW=292" alt="Logo" width="100" height="100">
 </a>
</div>

<p align="right">(<a href="#top">back to top</a>)</p>
