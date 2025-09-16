# Hallucinations (Confabulations)
1. `_in_features = model.classifier[13].in_features_` [GPT-5 likes the number 13 when it comes to indexing:-)]
   * **Error** Index 13 did not exist (it should have been index 1 instead)
2. `_ax.plot()_` in subplots (very common)
   * **Error**: Missed the subplot indexing (it should have been ax[0], ax[1],.. instead)
3. `CrossEntropyLR`
   * **Error** no such class definition exists in PyTorch (it should have been `CrossEntropyLoss` instead)
4. `cpu.is_bfloat16_supported()`
   * **Error** Pno such method `is_bfloat16_supported()` for CPU (however, cuda.is_bfloat16_supported() is available)
5. `streamer = streamers if len(streamers) > 1 else streamers`
   * `streamers` is a list; however, the if condition is redundant here!. Moreover, HF streamer doesn't natively support batch inputs (i.e., len(streamers)>1, it is always 1)
# Misc
1. It assumes you have an appropriate privilege to access critical resources in the SLURM server; therefore, `ProfileActivity.CUDA` throws the following error.
    * **Error**: function cbapi->getCuptiStatus() failed with error CUPTI_ERROR_INVALID_DEVICE (2) (insufficient privilege)
