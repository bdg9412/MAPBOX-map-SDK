# MAPBOX-map-SDK
Follow mapbox map SDK

## Map SDK documentaion  
Marker?  
// Icon 객체를 생성하여 drawable 폴더에 있는 마커 이미지를 할당합니다.  
IconFactory iconFactory = IconFactory.getInstance(MainActivity.this);  
Icon icon = iconFactory.fromResource(R.drawable.blue_marker);  
  
// 카메라의 타겟인 LatLng객체에 표현하고자 하는 마커의 좌표를 할당하여 사용합니다.  
mapboxMap.addMarker(new MarkerViewOptions()  
.position(new LatLng(-37.821648, 144.978594))  
.icon(icon));  

Map SDK – Camera  
Map SDK의 카메라는 맵위에서 사용자의 시점입니다. 따라서 우리가 지도어플을 사용하는 것처럼 우리는 카메라(시점)을 자유롭게 움직이며 지도위를 움직 일 수 있습니다.   
Map SDK는 CameraPosition 클래스를 가지고 있습니다. CameraPosition 클래스는 camera's target, angle, zoom, tilt, and padding을 포함합니다.  
CameraPosition position = new CameraPosition.Builder()  
	.target(new LatLng(51.50550, -0.07520))  
	.zoom(10)  
	.tilt(20)  
	.build();  
  
The Mapbox의 getCameraPosition 함수는 CameraPosition 클래스는의 함수로 현재 사용자가 무엇을 보고 있는지에 대해 알 수 있습니다.  
CameraPosition currentCameraPosition = mapboxMap.getCameraPosition();  
double currentZoom = currentCameraPosition.zoom;  
double currentTilt = currentCameraPosition.tilt;  
  
이와 함께 카메라를 이동시키거나 이동 구역을 제한할 수 있습니다. (https://docs.mapbox.com/android/maps/overview/camera/)  
