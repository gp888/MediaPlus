# MediaPlus
```
mCamera = Camera.open(Camera.CameraInfo.CAMERA_FACING_BACK);
      mParams = mCamera.getParameters();
      setCameraDisplayOrientation(this, Camera.CameraInfo.CAMERA_FACING_BACK, mCamera);
      mParams.setPreviewSize(SRC_FRAME_WIDTH, SRC_FRAME_HEIGHT);
      mParams.setPreviewFormat(ImageFormat.NV21); //preview format：NV21
mParams.setFocusMode(Camera.Parameters.FOCUS_MODE_CONTINUOUS_VIDEO);
      m_camera.setDisplayOrientation(90);
      mCamera.setParameters(mParams); // setting camera parameters
      m_camera.addCallbackBuffer(m_nv21);
      m_camera.setPreviewCallbackWithBuffer(this);
      m_camera.startPreview();

  @Override
  public void onPreviewFrame(byte[] data, Camera camera) {
      // TODO Auto-generated method stub
              //data这里就是获取到的NV21数据

      m_camera.addCallbackBuffer(m_nv21);//这里要添加一次缓冲，否则onPreviewFrame可能不会再被回调
  }
  ```
