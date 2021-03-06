`libvmaf` -- A Static LIBRARY of VMAF
===================

VMAF is now packaged into a library called `libvmaf`. You can install the library built using object files under wrapper/obj and ptools.

To install the library `libvmaf.a `run:

```
make install
```

This copies the library header `libvmaf.h` under `usr/local/include`, library `libvmaf.a `under `user/local/lib` and all the model files under `usr/local/share`. You can use the header `libvmaf.h` in your program. It contains an API which can be called from any C/C++ program:

```
int compute_vmaf(double* vmaf_score, char* fmt, int width, int height, 
int (*read_frame)(float *ref_data, float *main_data, float *temp_data, int stride, void *user_data), 
void *user_data, char *model_path, char *log_path, char *log_fmt, int disable_clip, 
int disable_avx, int enable_transform, int phone_model, int do_psnr, int do_ssim, 
int do_ms_ssim, char *pool_method, int thread, int subsample, int enable_conf_interval);
```

Here, `read_frame` is a callback function which can be used to pass data from a program to VMAF. `user_data` is a program specific data that can be used by the callback function. For sample usage of `compute_vmaf`, refer to [`wrapper/src/main.cpp`](wrapper/src/main.cpp).

To uninstall the library run:

```
make uninstall
```

