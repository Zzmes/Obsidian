```bash
# VPN
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 no_proxy="localhost,127.0.0.1

# CUDA
export CUDA_DIR=/usr/local/cuda
export PATH=$CUDA_DIR/bin:$PATH
export LD_LIBRARY_PATH=$CUDA_DIR/lib64:$LD_LIBRARY_PATH
export LIBRARY_PATH=$CUDA_DIR/lib64:$LIBRARY_PATH

# TensorRT
export TENSORRT_DIR=/workspace/tools/lib/TensorRT
export PATH=${TENSORRT_DIR}/bin:$PATH
export LD_LIBRARY_PATH=${TENSORRT_DIR}/lib:$LD_LIBRARY_PATH
export LIBRARY_PATH=${TENSORRT_DIR}/lib:$LIBRARY_PATH

# LibTorch
export Torch_DIR=/workspace/tools/lib/libtorch
export LD_LIBRARY_PATH=${Torch_DIR}/lib:$LD_LIBRARY_PATH
```