# Lina-Speech: Gated Linear Attention is a Fast and Parameter-Efficient Learner for text-to-speech synthesis
https://arxiv.org/abs/2410.23320
Théodor Lemerle, Harrison Vanderbyl, Vaibhav Srivastav, Nicolas Obin, Axel Roebel.

Code and checkpoints incoming...

# lina-speech (beta)

Exploring "linear attention" for text-to-speech.

It predicts audio codec "à la" [MusicGen](https://arxiv.org/abs/2306.05284) : delayed residual vector quantizers so that we do not need multiple models.

Featuring [RWKV](https://github.com/BlinkDL/RWKV-LM), [Mamba](https://github.com/state-spaces/mamba), [Gated Linear Attention](https://github.com/sustcsonglin/flash-linear-attention).

Compared to other LM TTS model :
- Can be easily pretrained and finetuned on midrange GPUs.
- Tiny memory footprint.
- Trained on long context (up to 2000 tokens : ~27s).

### Models

| Model | #Params | Dataset | Checkpoint | Steps | Note |
| :---: | :---: |:---: |:---: |:---: |:---: |
| GLA | 60M, 130M | Librilight-medium | [Download](https://huggingface.co/lina-speech/all-models/tree/main) | 300k | GPU inference only |
| Mamba| 60M | Librilight-medium |[Download](https://huggingface.co/lina-speech/all-models/tree/main)| 300k | GPU inference only |
| RWKV v6 | 60M | LibriTTS |[Download](https://huggingface.co/lina-speech/all-models/tree/main) | 150k | GPU inference only |

### Installation
Following the linear complexity LM you choose, follow respective instructions first:
- For Mamba check the [official repo](https://github.com/state-spaces/mamba).
- For GLA/RWKV inference check [flash-linear-attention](https://github.com/sustcsonglin/flash-linear-attention).
- For RWKV training check [RWKV-LM](https://github.com/BlinkDL/RWKV-LM)

### Inference

Download configuration and weights above, then check `Inference.ipynb`.

### TODO

- [x] Fix RWKV6 inference and/or switch to FLA implem.
- [ ] Provide a Datamodule for training (_lhotse_ might also work well).
- [ ] Implement CFG.
- [ ] Scale up.

### Acknowledgment

- The RWKV authors and the community around for carrying high-level truly opensource research.
- @SmerkyG for making my life easy at testing cutting edge language model.
- @lucidrains for its huge codebase.
- @sustcsonglin who made [GLA and FLA](https://github.com/sustcsonglin/flash-linear-attention).
- @harrisonvanderbyl fixing RWKV inference.

### Cite
```bib
@software{lemerle2024linaspeech,
  title  = {LinaSpeech: Exploring "linear attention" for text-to-speech.},
  author = {Lemerle, Théodor},
  url    = {https://github.com/theodorblackbird/lina-speech},
  month  = april,
  year   = {2024}
}
```
### IRCAM

This work is performed in the [Analysis/Synthesis team of the STMS Laboratory](https://www.stms-lab.fr/team/analyse-et-synthese-des-sons/) at IRCAM, and is part of the following project: 
[ANR Exovoices](https://anr.fr/Projet-ANR-21-CE23-0040)

<img align="left" width="150"  src="https://github.com/theodorblackbird/lina-speech/assets/1331899/7391b3c2-ec9a-431e-a090-f2ac5f55026b">
<img align="left" width="150"  src="logo_ircam.jpeg">
<img align="left" width="150" src="https://github.com/theodorblackbird/lina-speech/assets/1331899/74cc1ade-be95-4087-9cc1-83af6d7a54be">
<img align="left" width="150" src="https://github.com/theodorblackbird/lina-speech/assets/1331899/fc0ae259-26ae-451b-8893-80471255479d">


