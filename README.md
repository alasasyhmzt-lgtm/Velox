package A;

import J.j;
import android.hardware.camera2.CameraDevice;

public final class A extends CameraDevice.StateCallback {
    public final CameraDevice.StateCallback a;
    public final j b;

    public A(j jVar, CameraDevice.StateCallback stateCallback) {
        this.b = jVar;
        this.a = stateCallback;
    }

    public final void onClosed(CameraDevice cameraDevice) {
        this.b.execute(new z(this, cameraDevice, 0));
    }

    public final void onDisconnected(CameraDevice cameraDevice) {
        this.b.execute(new z(this, cameraDevice, 1));
    }

    public final void onError(CameraDevice cameraDevice, int i) {
        this.b.execute(new o(this, cameraDevice, i, 1));
    }

    public final void onOpened(CameraDevice cameraDevice) {
        this.b.execute(new z(this, cameraDevice, 2));
    }
}
