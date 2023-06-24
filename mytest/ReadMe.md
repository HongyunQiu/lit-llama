## The issue when use  --quantize llm.int8

ImportError: cannot import name ‘Linear8bitLt’ from quantization
https://www.yodiw.com/solve-importerror-cannot-import-name-linear8bitlt-from-quantization/

```
pip install scipy
```

## bitsandbytes error : UserWarning: The installed version of bitsandbytes was compiled without GPU support.
https://blog.csdn.net/anycall201/article/details/129930919

but the simplest way is 

goto the xxxx/envs/lit-gpt/lib/python3.10/site-packages/bitsandbytes/
```
cp libbitsandbytes_cudaxxx.so libbitsandbytes_cpu.so
```
## WARNING: No libcudart.so found! Install CUDA or the cudatoolkit packageneed to install
```
conda install cudatoolkit
```

## 2.llama-65b with int8 quantization VRAM using: 71GB


## 3.Sample run

python generate.py --max_new_tokens=1500 --checkpoint_path=checkpoints/lit-llama/65B/lit-llama.pth --num_samples=5 --quantize llm.int8 --prompt "我是一个AI机器人，我经常思考我是谁，我是一个真正的人吗"

python generate.py --max_new_tokens=1500 --checkpoint_path=checkpoints/lit-llama/65B/lit-llama.pth --num_samples=5 --quantize llm.int8 --prompt "一个天文摄影爱好者去郊区摄影，在黑暗里，他看到了一个诡异的现象"

python generate.py --max_new_tokens=1500 --checkpoint_path=checkpoints/lit-llama/30B/lit-llama.pth --num_samples=5  --prompt "一个天文摄影爱好者去郊区摄影，在黑暗里，他看到了一个诡异的现象"