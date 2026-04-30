# FastCrest

**Deploy any robot AI model to any edge GPU. One command.**

FastCrest builds [Reflex](https://github.com/FastCrest/reflex-vla), the open-source deployment layer for Vision-Language-Action (VLA) models — pi0, pi0.5, SmolVLA, NVIDIA's GR00T, OpenVLA. We collapse a month of CUDA / ONNX / TensorRT glue into one command (`pip install reflex-vla && reflex go --model smolvla-base`) with verified bit-for-bit numerical parity to the PyTorch reference.

## Why we exist

Robotics teams training VLAs hit a wall at deployment. Most spend a month writing CUDA, ONNX, and TensorRT glue to get a single checkpoint running on a Jetson. Even after that, the export usually breaks numerically without anyone noticing until the robot misbehaves on real hardware. That silent action-drift is the most expensive class of bug in the field. Reflex eliminates it.

## Highlights

- **Verified cos=+1.000000 ONNX parity** across SmolVLA, pi0, pi0.5, GR00T N1.6, OpenVLA at machine precision. Five architectures, one tool.
- **9.79× speedup on decomposed pi0.5** via VLM-prefix + expert-denoise split with KV cache reuse.
- **5.55× speedup from TensorRT** by default in v0.7+; **4.44× more from CUDA graphs** on A100, p99 latency down 30%, jitter 4.1× tighter.
- **First public reproduction of SnapFlow 1-NFE distillation** — pi0.5 student scores 29/30 on LIBERO, beats the 10-step teacher's 28/30, fits an 8 GB Jetson Orin Nano.
- **Continuous self-distilling serve** ($99/mo Pro tier) hot-reloads a customer-specific 1-step student every few hours from real /act traffic.

## Repos

| Repo | What | Status |
|---|---|---|
| [reflex-vla](https://github.com/FastCrest/reflex-vla) | The open-source CLI. `pip install reflex-vla` | Public, BSL 1.1 |

## Where to find us

- **Site:** https://fastcrest.com
- **Discord:** https://discord.gg/wrPUdcxdPu
- **PyPI:** https://pypi.org/project/reflex-vla/
- **Email:** team@fastcrest.com

## License

[BSL 1.1](https://github.com/FastCrest/reflex-vla/blob/main/LICENSE) — same model HashiCorp, MongoDB, Sentry, and Cockroach use. Free for personal, internal, and customer-facing commercial use; restricts only competing hosted/embedded offerings. Auto-converts to Apache 2.0 in four years.

---

Building toward the deployment layer of the robotics era. **Software wedge → hardware bundles → silicon → datacenter.** [Read the full vision](https://discord.gg/wrPUdcxdPu) on Discord.
