

# download


hf download unsloth/Qwen3.5-35B-A3B-GGUF \
  --include Qwen3.5-35B-A3B-UD-Q4_K_XL.gguf \
  --include "mmproj-F16.gguf" \
    --local-dir ~/models/Qwen3.5-35B-A3B-GGUF





# LLAMA CPP RUN

GGML_CUDA_GRAPH_OPT=1
CUDA_SCALE_LAUNCH_QUEUES=4x

~/llama.cpp/build/bin/llama-server
--model ~/models/Qwen3.5-27B-GGUF/Qwen3.5-27B-UD-Q4_K_XL.gguf
--mmproj ~/models/Qwen3.5-27B-GGUF/mmproj-F16.gguf
--alias Qwen3.5-27B-GGUF
--host 0.0.0.0
--port 30000
--flash-attn on
--no-mmap
--jinja
--fit on
--ctx-size 32768



