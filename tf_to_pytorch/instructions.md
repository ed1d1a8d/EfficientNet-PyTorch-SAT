1.  Run the following commands:
    ```
    cd tf_to_pytorch
    pip install gdown

    cd pretrained_tensorflow
    python download_sat.py --model_name efficientnet-bL1-enhanced
    cd ..
    ```

2. Add a file called `checkpoint` in the `pretrained_tensorflow/efficientnet-bL1-enhanced` directory with the following contents:
   ```
   model_checkpoint_path: "efficientnet-bL1-enhanced"
   all_model_checkpoint_paths: "efficientnet-bL1-enhanced"
   ```

3.  Run the following commands
    ```
    mkdir -p pretrained_pytorch
    cd convert_tf_to_pt
    python load_tf_weights.py \
        --model_name efficientnet-bL1 \
        --tf_checkpoint ../pretrained_tensorflow/efficientnet-bL1/ \
        --output_file ../pretrained_pytorch/efficientnet-bL1.pth
    ```
