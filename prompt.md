Follow mostly everything here AxiomicLabs/GPT-X3-150M @ Hugging Face
Ok So spawn subagents that are going to make the code from data prep(upload to Coderofpears/Shards Make the repo), then train the model on our hardware. You will use the browser to secure Google Colab,Modal,and Kaggle Notebooks compute. Then you will do offline RL on my 5060ti(You are running on that machine.) Then Upload the model to hf as private and delete the shards. Then try as hard as you can locally to train the model to be better. I want a model with an Artificial Analysis Score of higher than 35. Benchmark the model. Do not be afraid to spawn Subagents
Try and train on 100b tokens, but at minimum train on 50b tokens. I have 8.9 dollars in openrouter credits. Make a distillation dataset with openai batch on openrouter(it exists) or with claude sonnet 5.5 batch. This will be a general purpose model. Train it to think with CoT. Make sure there are no bugs and if needed, use Ngrok to communicate between devices. On this pc(5060ti) do not download too much because this is home wifi. I will come back in a week or 2. See you in a week. Do status updates every 2 hours to
```/output/status/```. You may use TPU if you deem it ok. If my codex limit is going down, use opencode zen's deepseek v4.1 flash free, or opencode zen's mimo 2.6 flash.
-Live Model Modification
# Pear1.5 Model Project Brief

## Mission

Build and evaluate Pear1.5, a general-purpose language model, using the available local machine and any explicitly authorized compute. Work incrementally: first establish a reproducible, working baseline, then improve it. Do not promise a target score or training-token count before measuring feasibility.

## Research directions

Investigate these as candidate capabilities, not requirements to implement all at once:

- Multiple context lengths or context-management strategies
- Selective enabling and disabling of model layers
- Tool use
- Offline reinforcement learning
- Mixture of LoRAs (MoL)
- Unified multimodal training
- Live model modification

Use `AxiomicLabs/GPT-X3-150M` on Hugging Face as a reference. Inspect its architecture, training approach, license, and available artifacts first; treat it as a reference rather than assuming every design choice should be copied. Record sources and uncertainties.

## Execution plan

1. **Inspect and plan.** Review this repository, the available hardware (including GPU memory and disk), installed software, network limits, and the reference model. Check current provider availability, terms, and pricing. Estimate the compute and storage required for a 50B- and 100B-token run before downloading large datasets or starting jobs.
2. **Build the data pipeline.** Create reproducible data preparation, filtering, deduplication, validation, and dataset versioning. If authorized and feasible, publish prepared shards to `Coderofpears/Shards`. Keep secrets out of code, logs, and datasets.
3. **Establish a baseline.** Implement or adapt the smallest training path that can be tested end to end. Add focused tests, document commands and configuration, and run a short smoke training job before scaling up.
4. **Scale only when justified.** Consider local hardware, Colab, Modal, Kaggle, or TPU only after checking availability and estimating cost, quotas, runtime limits, and data movement. Do not create paid resources, accept terms, or use account credentials without explicit authorization. Stop and report if the target token count is not feasible within the available compute, time, and budget; prioritize a reproducible model over an unverified token-count claim.
5. **Distill and train.** The available OpenRouter budget is **$8.90 maximum**. Verify that the proposed batch API, model, and pricing are currently supported before use. Track spend and stop before exceeding the cap. Do not assume a model or API (including “Claude Sonnet 5.5”) exists or is accessible. Generate high-quality examples with answers and concise, user-facing rationales; do not collect or train on private hidden chain-of-thought. Keep a held-out evaluation set separate from training data.
6. **Evaluate and improve.** Benchmark the baseline and each material change using reproducible, appropriate evaluations for quality, tool use, and multimodal tasks when applicable. Report methods, model revision, results, and limitations. Treat an Artificial Analysis score above 35 as an aspirational target, not a guarantee; use a comparable, public evaluation and do not imply an official score unless it was actually obtained through the relevant evaluation process. Apply offline RL only after a validated baseline and a documented reward/evaluation design.
7. **Publish and clean up.** Upload the final selected model to Hugging Face as a private repository only after the user authorizes the destination and the artifacts pass validation. Verify the upload and retain a recoverable copy before deleting any shards. Never delete the only copy of data or model artifacts.

## Operating constraints

- The local machine has an NVIDIA RTX 5060 Ti. Confirm actual hardware and memory rather than assuming them. Minimize downloads and avoid repeatedly transferring large datasets over the home connection; prefer resumable transfers and checksums.
- Use subagents for independent, bounded work when available, and review their changes. Keep the main implementation, configuration, and experiment records in this repository.
- Use Ngrok or another tunnel only when necessary, with authentication and the smallest practical exposure. Never expose credentials, private datasets, or an unauthenticated training service.
- Do not modify unrelated personal files or make irreversible system changes. Ask before destructive cleanup, broad system configuration changes, or actions that incur costs beyond the stated budget.
- Do not claim the project will run continuously while the agent is offline. Work only while execution is available, checkpoint long jobs, and leave clear resume instructions.
- If coding-model quota becomes a constraint, consider the free OpenCode Zen DeepSeek V4.1 Flash or MiMo 2.6 Flash options only after verifying current availability and data-handling terms. Do not send secrets or private data to third-party services.

## Progress and deliverables

Write concise status reports to `/output/status/` at meaningful milestones and, if a process is genuinely running continuously, no more than every two hours. Each report should include the timestamp, completed work, current run or blocker, resource/budget use, and next step. If the directory is unavailable, report that and keep status in the repository.

Deliver:

- Reproducible setup, data, training, and evaluation instructions
- Tested code and configuration, with known limitations documented
- Dataset/model versions and checksums where applicable
- Training logs and benchmark results, including actual token count and compute used
- A private Hugging Face model only if upload was authorized and verified
- A final summary distinguishing completed work, measured results, estimates, and remaining work

Start with inspection and a feasibility report. Do not begin large downloads, paid compute, public uploads, or destructive deletion until the relevant authorization and feasibility checks are complete.
You may have full access of this PC.
