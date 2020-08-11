
# ARFoundation in Android for tracking image
_Tài liệu tìm hiểu: lý thuyết [AR Foundation](https://unity.com/unity/features/arfoundation) của [Unity](https://unity.com) và thực hành cài đặt tính năng Image Tracking trên Android_

**Mã nguồn**:  https://github.com/ngankhanh98/ARFoundation

## Mục lục

  * [AR Foundation](#ar-foundation)
    + [AR Foundation features](#ar-foundation-features)
    + [Các lớp được hỗ trợ](#các-lớp-được-hỗ-trợ)
  * [AR Foundation trong Unity](#ar-foundation-trong-unity)
    + [Chuẩn bị](#chuẩn-bị)
    + [Cài đặt](#cài-đặt)
      - [**Tạo AR Foundation project**](#**tạo-ar-foundation-project**)
      - [**Cài đặt ARCore và ARKit**](#**cài-đặt-arcore-và-arkit**)
      - [**Build setting**](#**build-setting**)
  * [References](#references)


## AR Foundation
AR Foundation là một framework do Unity cung cấp, dành riêng cho phát triển ứng dụng Thực tại ảo, cho phép triển khai trên các thiết bị di động và các thiết bị trải nghiệm thực tế ảo.
### AR Foundation features
Fonctionality | ARCore | ARKit | Magic Leap | HoloLens
------------- | ------ | ----- | ---------- |---------
Device tracking|✔|✔|✔|✔|
Plane tracking|✔|✔|✔||
Point clouds|✔|✔|||
Anchors|✔|✔|✔|✔|
Light estimation|✔|✔|||
Environment probes|✔|✔|||
Face tracking|✔|✔|✔||
Meshing|||✔|✔|
2D Image tracking|✔|✔|||
Raycast|✔|✔|✔||
Pass-through video|✔|✔|||
Session management|✔|✔|✔|✔|

### Các lớp được hỗ trợ

Trackable Manager | Trackable | Purpose
----------------- | --------- | -------
ARPlaneManager |ARPlane| 	A manager for ARPlanes. Creates, updates, and removes GameObjects in response to detected surfaces in the physical environment.
ARPointCloudManager| 	ARPointCloud	| Detects feature points.
ARAnchorManager| 	ARAnchor	| Manages anchors. You can manually add and remove them with`ARAnchorManager.AddAnchor` and`ARAnchorManager.RemoveAnchor.`
ARRaycastManager	| ARRaycast| 	Manages an `XRRaycastSubsystem`, exposing raycast functionality in ARFoundation. Use this component to raycast against trackables (i.e., detected features in the physical environment) when they do not have a presence in the Physics world.
ARTrackedImageManager| 	ARTrackedImage| 	A manager for ARTrackedImages. Uses the`ARImageTrackingSubsystem` to recognize and track 2D images in the physical environment.
AREnvironmentProbeManager| 	AREnvironmentProbe	| Creates cubemaps that represent the environment.
ARFaceManager	| ARFace| 	Detects and tracks human faces.
ARTrackedObjectManager| 	ARTrackedObject	| Detects 3D objects.
ARParticipantManager	| ARParticipant| 	Tracks other users in a multi-user collaborative session.

## AR Foundation trong Unity
### Chuẩn bị
- Tải và cài đặt [**Unity Personal**](https://store.unity.com/?_ga=2.126206861.180657599.1597112384-1639346226.1596684768#plans-individual)
- Thêm module cần thiết. Trong **Unity Hub**, ở tab **Install** > chọn version Unity > **Add modules**. Chọn **Android Build Support** hoặc/và **iOS Build Support** > **Done**

 ![](https://i.imgur.com/e8qP2cO.png)


### Cài đặt
#### **Tạo AR Foundation project**
Mở **Unity Hub**, trong tab **Projects**, chọn **NEW**, nhập **Project Name** và **Location** như bình thường với **Templates** 3D. Xong, chọn **CREATE**

![](https://i.imgur.com/pNnGBGS.png)

#### **Cài đặt ARCore và ARKit**
Theo [About AR Foundation](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@4.1/manual/index.html), để sử dụng AR Foundation, cần cài đặt thêm một vài plugin dành riêng cho loại thiết bị:
- ARCore XR Plugin cho Android
- ARKit XR Plugin cho iOS
- Magic Leap XR Plugin cho Magic Leap
- Windows XR Plugin cho HoloLens

Trên menu bar, chọn **Window** > **Package Manager**. Trong cửa sổ Package Manager, cài đặt 3 plugin: **AR Foundation**, **ARCore XR Plugin** và **ARKit XR Plugin**

![](https://i.imgur.com/AjAHTVC.png)

#### **Build setting**
Sau khi hoàn thành, hiệu chỉnh để ứng dụng có thể build trên các target platform.
Trên menu bar, chọn **Build Settings...**. Trong Build Settings windows, chọn target platform (**Android** hoặc **iOS**...) > **Switch Platform** > **Build And Run**
![](https://i.imgur.com/l0bvaKR.png)

Với Android, bạn cần có [**ARCore supported devices**](https://developers.google.com/ar/discover/supported-devices) để cài đặt **.apk** đã được build.

## References
- [Unity - Manual:  Unity User Manual (2019.4 LTS)](https://docs.unity3d.com/Manual/index.html)
- [Unity's AR Foundation Frameword](https://unity.com/unity/features/arfoundation)
- [Youtube: AR Foundation & Unity 03: Image Tracking](https://www.youtube.com/watch?v=o_z_Eb8Yh2g&t=548s)