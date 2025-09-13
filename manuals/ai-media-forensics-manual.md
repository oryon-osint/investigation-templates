# 🛰️ AI Media Forensics Manual  
### Practical Techniques for Detecting Synthetic Media  

![Version](https://img.shields.io/badge/version-v1.0.0-blue)   
![Last Update](https://img.shields.io/badge/updated-2025--09--13-red)

## 1. Introduction

Artificial Intelligence has enabled the creation of hyper-realistic synthetic media — images, video, audio, and text that can convincingly mimic authentic content. While AI brings innovation in media production, it also introduces risks: misinformation campaigns, reputational attacks, political manipulation, and cyber-enabled fraud.

This manual is designed for journalists, investigators, analysts, and digital forensic professionals. It delivers:

- A **structured methodology** for content verification.
    
- A **multi-phase workflow** that scales from rapid screening to evidentiary forensics.
    
- A **toolkit of practical technologies** aligned with OSINT and DFIR practices.
    
- **Best practices** for documentation, reporting, and transparency.
    

## 2. Analysis Models

The detection process is divided into four escalating phases:

1. **Rapid Triage (Initial Screening)** – Quick suspicion check.
    
2. **Preliminary Verification (Lightweight Checks)** – OSINT-based fast validation.
    
3. **Structured Forensic Analysis (In-Depth Review)** – Comprehensive forensic-grade methods.
    
4. **Peer Review & Validation (Cross-Check)** – Independent replication to reduce bias.
    

## 3. Detection Domains

**How to use this section:** Each domain targets a distinct failure mode common to synthetic media. Treat domains as **independent lines of evidence**. A single red flag rarely proves anything; **two or more from different domains** justifies escalation.

### 3.1 Anatomy & Object Integrity

**Objective:** Detect biological or object construction errors introduced by generative AI.

**Indicators:**

- Extra, missing, or fused fingers; malformed nails; symmetrical eyes without natural variation.
    
- Teeth rendered as uniform blocks or inconsistent with gum lines.
    
- Ears, earrings, or glasses distorted or asymmetrical.
    
- Clothing, fabric, or accessories with warped stitching, inconsistent patterns, or impossible geometry.
    

**Checks:**

- Zoom to 200–400% and scan hands, eyes, and teeth.
    
- Look for repeated face patterns in group shots.
    
- Compare mirrored body parts for natural asymmetry.
    

**Tools:** [Forensically](https://29a.ch/photo-forensics/), magnifiers, reverse image search on cropped anomalies.

### 3.2 Geometry & Physics

**Objective:** Test whether light, perspective, and reflections obey physical laws.

**Indicators:**

- Shadows inconsistent with light sources or each other.
    
- Reflections missing in mirrors, water, or glass.
    
- Vanishing points misaligned; horizon misplaced.
    
- Object scale inconsistent with distance.
    

**Checks:**

- Use SunCalc to validate shadow length vs. claimed time/place.
    
- Draw vanishing lines to test perspective.
    
- Inspect reflections for parity and content.
    

**Tools:** [SunCalc](https://www.suncalc.org/), Google Earth/Street View, [Forensically](https://29a.ch/photo-forensics/).

### 3.3 Metadata & Technical Fingerprints

**Objective:** Analyze embedded metadata and camera/device signatures.

**Indicators:**

- Missing EXIF in photos that should contain it.
    
- Impossible timestamps or GPS coordinates.
    
- Software tags showing AI editors or generators.
    
- Uniform synthetic noise lacking natural PRNU (Photo Response Non-Uniformity).
    

**Checks:**

- Run ExifTool to review `Make/Model`, `DateTimeOriginal`, `GPS` fields.
    
- Inspect compression signatures and quantization tables.
    
- Apply Noiseprint for sensor fingerprinting.
    

**Tools:** [ExifTool](https://exiftool.org/), [FotoForensics](http://fotoforensics.com/), [Noiseprint](https://github.com/isi-vista/noiseprint).

### 3.4 Voice & Audio

**Objective:** Identify synthetic patterns in speech or environmental sound.

**Indicators:**

- Robotic cadence; unnatural prosody.
    
- Missing breathing, mouth clicks, or ambient noise.
    
- Spectrogram anomalies: clean high frequencies, banding.
    

**Checks:**

- Inspect spectrograms for unnatural frequency bands.
    
- Measure jitter/shimmer in Praat for vocal variation.
    
- Compare lip sync to phonemes in video.
    

**Tools:** [Audacity](https://www.audacityteam.org/), [Praat](https://www.fon.hum.uva.nl/praat/), Deepware Scanner, Intel FakeCatcher.

### 3.5 Contextual Consistency

**Objective:** Confirm claimed time, place, and environment.

**Indicators:**

- Seasonal mismatch (snow vs. claimed summer).
    
- Buildings or skylines inconsistent with stated location.
    
- Weather contradicting meteorological records.
    

**Checks:**

- Validate shadows and lighting with SunCalc.
    
- Compare weather with Meteostat or OGIMET logs.
    
- Cross-reference landmarks via Google Earth or Street View.
    

**Tools:** [Meteostat](https://meteostat.net/), [OGIMET](https://www.ogimet.com/), [Google Earth](https://earth.google.com/).

### 3.6 Behavioral & Social Signals

**Objective:** Assess realism of group dynamics and human behavior.

**Indicators:**

- Identical faces or clothing repeated in crowds.
    
- People ignoring focal events (all gazes in wrong direction).
    
- Uniform expressions or synchronized gestures.
    

**Checks:**

- Run face clustering to detect duplicates.
    
- Check gaze direction consistency.
    
- Observe micro-expressions and natural motion.
    

**Tools:** [InVID](https://www.invid-project.eu/tools-and-services/invid-verification-plugin/), Forensically.

### 3.7 Textual AI Fingerprints

**Objective:** Detect linguistic artifacts of AI-generated text.

**Indicators:**

- Repetitive scaffolding or formulaic phrasing.
    
- Fabricated citations or unverifiable facts.
    
- Uniform sentence lengths and transitions.
    

**Checks:**

- Run AI detectors on samples.
    
- Perform stylometric comparison to known author texts.
    
- Spot-check quotes and references.
    

**Tools:** [GLTR](http://gltr.io/), [DetectGPT](https://github.com/eric-mitchell/detect-gpt), [HuggingFace Models](https://huggingface.co/), JStylo.

### 3.8 Provenance & Watermarking

**Objective:** Identify provenance credentials or embedded watermarks.

**Indicators:**

- Valid C2PA signatures showing edit history.
    
- Invisible watermarks indicating AI generation.
    

**Checks:**

- Extract provenance JSON and verify signatures.
    
- Run SynthID or watermark scanners where available.
    

**Tools:** [C2PA](https://c2pa.org/), Adobe Content Credentials, Google SynthID.

### 3.9 AI-vs-AI Detection

**Objective:** Apply specialized AI detectors trained to spot generative content.

**Indicators:**

- High detector confidence across multiple frames.
    
- Consistent outputs from different models.
    

**Checks:**

- Apply forensic CNNs (XceptionNet, FaceForensics++).
    
- Compare results across multiple detectors.
    

**Tools:** [FaceForensics++](https://github.com/ondyari/FaceForensics), DFDC models, XceptionNet-based classifiers.

### 3.10 Cross-Modal & Narrative Consistency

**Objective:** Ensure all media modalities align with the narrative.

**Indicators:**

- Lip sync mismatch between audio and video.
    
- Weather sounds inconsistent with visual conditions.
    
- Narration contradicting imagery.
    

**Checks:**

- Align timestamps across text, audio, and video.
    
- Verify environment acoustics match visual context.
    
- Map camera positions vs. scene constraints.
    

**Tools:** CrossCheck, [SensityAI](https://sensity.ai/), Reality Defender.

## 4. Step-by-Step Procedures. Step-by-Step Procedures

This section provides an operational, reproducible workflow from first contact with a file/link to an evidence‑grade conclusion. It is organized into **four phases**. Each phase includes objectives, inputs, actions, tools, outputs, and escalation criteria.

### 4.0 Pre‑Flight: OPSEC & Chain of Custody (CoC)

**Objective:** Preserve evidentiary integrity and avoid contaminating artifacts.

**Inputs:** Source URL, file(s), claims (who/what/where/when), stakeholder urgency.

**Actions:**

- **Acquire original** if possible (avoid platform‑compressed versions). Request raw files via secure channel.
    
- **Hash immediately:**
    
    - Bash/macOS: `shasum -a 256 <file>`
        
    - PowerShell: `Get-FileHash <file> -Algorithm SHA256`
        
- **Snapshot context:** copy URL, post ID, author handle, timestamps (include time zone), and a screenshot of the claim.
    
- **Workspace:** operate on a **copy**; never re‑encode originals. Record tool names & versions.
    
- **Risk & scope:** decide if this is _routine verification_ or _high‑stakes_ (elections, conflict, criminal case).
    

**Output:** Case record with IDs, hashes, source notes, and a plan for Phase 1.

### 4.1 Rapid Triage (Initial Screening)

**Objective:** Decide in seconds whether the material merits deeper checks.

**Inputs:** One image/video frame, short audio snippet, or text excerpt.

**Actions (by media type):**

- **Image/Video frame:**
    
    - **Anatomy & objects:** hands, eyes, teeth, ears, accessories, signage, logos.
        
    - **Physics:** shadow direction/length, reflections, specular highlights; lighting continuity.
        
    - **“Too perfect” test:** cinematic composition, hyper‑clean surfaces, uniform faces.
        
- **Audio:** listen for breath/pauses, monotone prosody, robotic shimmer at pitch changes.
    
- **Text:** repetitive phrasing, encyclopedic tone, confident statements without sources.
    

**Common red flags:** extra/merged fingers; mismatched shadows; mirrored or unreadable micro‑text; cloned textures; lip‑sync oddities; identical smiles.

**False positives:** heavy denoise/HDR; professional retouching; platform recompression; staged marketing visuals.

**Output:** **Triage code** — Green (plausible), Amber (suspicious), Red (multiple anomalies). Amber/Red → Phase 2.

### 4.2 Preliminary Verification (Lightweight Checks)

**Objective:** Use fast OSINT & basic forensic tools to confirm or challenge authenticity.

**Inputs:** Original (preferred) or best‑quality copy; claimed time/place/context.

**Tools (typical):** Google/Bing/Yandex Images; InVID‑WeVerify; ExifTool; Forensically / FotoForensics; Noiseprint; SunCalc; Timeanddate/Meteostat/OGIMET; Google Earth/Street View.

**Step‑by‑step:**

1. **Reverse search (image/video):**
    
    - If video, extract 4–12 **keyframes** (InVID → Keyframes or `ffmpeg -i input.mp4 -vf fps=1 frames/f%04d.jpg`).
        
    - Search the **full image** plus **cropped regions** (faces, signs, skyline). Try **horizontal flip** when relevant.
        
    - Compare hits: earlier appearances, different captions, stock/AI galleries.
        
2. **Metadata inspection (images/video/audio):**
    
    - `exiftool <file>` → review `Make/Model`, `Software`, `DateTimeOriginal`, `GPS*`.
        
    - Red flags: missing EXIF in camera JPEGs, impossible timestamps, odd `Software` (generator), GPS contradicting claim.
        
    - Caveat: social sites often strip/alter EXIF.
        
3. **Basic pixel forensics (images):**
    
    - **ELA/Clone/Noise** in Forensically/FotoForensics.
        
    - Red flags: isolated high ELA around inserted objects; tiled repeats; uniform noise where natural variation is expected.
        
    - **Noiseprint/PRNU hint:** lack of camera‑like noise structure can support suspicion.
        
4. **Context cross‑check (all media):**
    
    - **Place:** landmark geometry in Google Earth/Street View; signage language & fonts.
        
    - **Time/lighting:** SunCalc — does shadow azimuth/elevation match claimed date/time/location?
        
    - **Weather:** compare precipitation/clouds/temperature with Timeanddate/Meteostat/OGIMET.
        

**Evidence to capture:** screenshots of reverse‑search results; EXIF dumps; ELA/Noise overlays; SunCalc and weather pages (PDFs or images).

**Decision & escalation:**

- **Converging authentic signals** → document as _provisionally authentic_.
    
- **≥2 independent inconsistencies** → escalate to Phase 3.
    

### 4.3 Structured Forensic Analysis (In‑Depth Review)

**Objective:** Produce a defendable assessment using advanced methods across modalities.

**Inputs:** Highest‑quality media; claims; any prior investigative notes.

**Modules & procedures:**

**A) Video Forensics**

- **Frame extraction:**
    
    - Constant rate: `ffmpeg -i in.mp4 -vf fps=5 frames/f_%05d.jpg`
        
    - Scene changes: `ffmpeg -i in.mp4 -vf "select='gt(scene,0.5)'" -vsync vfr scenes/s_%05d.jpg`
        
- **Temporal artifacts:** look for warping/morphing around faces/hands; inconsistent motion blur; jitter on edges; rolling‑shutter realism during pans.
    
- **Optical flow/consistency:** check for motion coherence of shadows/reflections across frames.
    

**B) Audio Forensics**

- **Spectrogram analysis (Audacity):** View → Spectrogram; inspect harmonics, breath noise, plosives; spot copy‑paste bands.
    
- **Prosody/phonation (Praat):** measure pitch (F0), jitter/shimmer; overly uniform patterns suggest synthesis.
    
- **Deepfake detectors:** run Resemble Detect / Deepware; treat as **supporting**, not decisive.
    
- **Physiological cues:** where applicable, evaluate biometric pulse cues (e.g., FakeCatcher‑style signals) with caution.
    

**C) Text Stylometry**

- Establish a **baseline** from verified writings (if authorship is at issue).
    
- Analyze with JStylo (function words, POS patterns, sentence length variance).
    
- Cross‑check with GPTZero/DetectGPT/HuggingFace classifiers; corroborate with factual verification (quotes, sources, dates).
    

**D) Contextual OSINT**

- **Geolocation:** skyline line‑drawing; terrain/river bends; sign typography; street furniture; license plates.
    
- **Chronology:** construction timelines (bridges, towers), event schedules, transport GTFS feeds.
    
- **Remote sensing:** Sentinel Hub/NASA Worldview for cloud cover, snow extent, wildfire smoke on claimed dates.
    

**E) Provenance & Watermarking**

- **C2PA/Content Credentials:** inspect with compatible viewers; export the provenance JSON; verify signatures and edit history.
    
- **SynthID/Watermarks:** where tooling is available, check invisible watermarks in images/audio/text; document limitations.
    

**F) Model‑Specific Forensics (AI‑vs‑AI)**

- Apply forensic CNNs (e.g., XceptionNet/FaceForensics++/DFDC models) on images/frames; **never as a sole indicator**. Record model type, version, thresholds, and confusion risks.
    

**G) PRNU / Camera Fingerprinting (expert option)**

- Extract sensor noise residuals; compare to a reference set of images from the purported device.
    
- Caveats: recompression, denoise, and resizing degrade PRNU; treat as corroborative.
    

**Outputs:**

- Annotated frames/spectrograms; tool outputs (versions, parameters); OSINT corroboration; a reasoned conclusion with **probability language** (see 4.5).
    

**Escalation triggers:** conflicting signals; high impact (elections, criminal proceedings); legal request for expert affidavit.

### 4.4 Peer Review & Validation (Cross‑Check)

**Objective:** Reduce bias and ensure reproducibility.

**Process:**

- Prepare a **neutral brief** (facts, methods, outputs) avoiding leading language.
    
- A second analyst **replicates** key steps (reverse search, EXIF, pixel/audio/text analysis, context checks) independently.
    
- Compare findings; document agreements and discrepancies; if needed, seek a third expert or additional data (original file, higher resolution, longer cut).
    

**Artifacts:** replication log, checklist of reproduced results, change log of conclusions.

**Outcome:** consensus conclusion or documented divergence with rationale.

### 4.5 Decision & Reporting Framework

**Probability bands (recommendation):**

- **Very Low (≤20%)** — unlikely AI‑generated.
    
- **Low (21–40%)** — weak indicators; more data recommended.
    
- **Indeterminate (41–59%)** — conflicting signals; seek originals or expert tests.
    
- **High (60–80%)** — multiple independent indicators of AI/manipulation.
    
- **Very High (>80%)** — strong, corroborated evidence across domains.
    

**Language examples:** _“High likelihood of AI generation based on [A, B, C], with no contradicting evidence. Limitations: [X, Y].”_

**Minimum evidence for publication (suggested):** ≥2 independent indicators from different domains **or** 1 strong forensic indicator + context contradiction.

### 4.6 Automation Recipes (Optional)

- **Batch EXIF export:**
    
    - `exiftool -csv -r -DateTimeOriginal -Make -Model -Software -GPS* <folder> > exif_report.csv`
        
- **Batch keyframes:**
    
    - `ffmpeg -i in.mp4 -vf fps=1 out/frame_%05d.jpg`
        
- **Scene change list:**
    
    - `ffmpeg -i in.mp4 -filter:v "select='gt(scene,0.4)',showinfo" -f null - 2> scenes.log`
        

**Tip:** Log tool versions and parameters alongside outputs for reproducibility.

### 4.7 Case Log Template (suggested fields)

- Case ID, Analyst, Date/Time (TZ), Source URL/ID, Acquisition method, File hashes (SHA‑256), Media type, Claimed context, Tools & versions, Steps performed, Findings per step, Indicators (pro/contra), Probability band, Peer reviewer, Final conclusion, Evidence archive location.
    

## 5. Best Practices

- **Two-signal principle:** Never conclude based on one indicator.
    
- **Documentation:** Maintain chain of custody (hashes, metadata, tool versions).
    
- **Probabilistic reporting:** Use “high likelihood” instead of absolutes.
    
- **Continuous adaptation:** Update methods every 6–12 months.
    
- **Automation:** Integrate tools into scripted pipelines.
    
- **Crowdsourced verification:** Collaborate with OSINT/fact-checking communities.
    

## 6. Analyst Toolkit (2025)

- **Images:** Forensically, FotoForensics, ExifTool, Noiseprint.
    
- **Video:** InVID, ffmpeg, FakeCatcher.
    
- **Audio:** Praat, Audacity, Resemble Detect, Deepware Scanner.
    
- **Text:** GPTZero, DetectGPT, JStylo, HuggingFace classifiers.
    
- **Provenance:** C2PA tools, Adobe Content Credentials, SynthID.
    
- **Context:** Google Earth, Sentinel Hub, Meteostat, NASA Worldview.
    
- **AI-forensics:** XceptionNet, FaceForensics++, DFDC models.
    

## 7. Strategic Outlook

- **Evolving AI:** Generation models are rapidly improving, masking older flaws.
    
- **Future of detection:** Watermarking, provenance standards, and blockchain-based verification will be critical.
    
- **Present reality:** Only a hybrid approach (intuition + OSINT + forensics + AI detectors + provenance tools) can sustain investigative integrity.
    

## Appendix A: Domain → Tools Matrix

|Detection Domain|Techniques|Tools (Open-Source / Free)|
|---|---|---|
|**Visual Forensics**|Identify anomalies: hands, eyes, teeth, reflections, shadows|[Forensically](https://29a.ch/photo-forensics/), Deepware Scanner, GIMP|
|**Metadata & File Integrity**|Extract & analyze EXIF, XMP, hashes, signatures|[ExifTool](https://exiftool.org/), Mat2, Hashdeep|
|**Error Level & Compression Analysis**|ELA, JPEG ghost detection, noiseprint mismatch|[FotoForensics](http://fotoforensics.com/), [Noiseprint](https://github.com/isi-vista/noiseprint)|
|**Reverse Image/Video Search**|Reverse search images/videos for provenance|[InVID-WeVerify](https://www.invid-project.eu/tools-and-services/invid-verification-plugin/), Yandex Images, TinEye|
|**Audio Forensics**|Spectrograms, waveform anomalies, deepfake audio classifiers|[Sonic Visualiser](https://www.sonicvisualiser.org/), [Praat](https://www.fon.hum.uva.nl/praat/), FakeCatcher (Intel)|
|**Textual Stylometry**|Stylometry, linguistic patterns, AI-text probability detectors|[GLTR](http://gltr.io/), [DetectGPT](https://github.com/eric-mitchell/detect-gpt), [HuggingFace Transformers](https://huggingface.co/)|
|**Context & OSINT Cross-Verification**|Cross-check geography, time, weather, events|[OSINT Framework](https://osintframework.com/), Wayback Machine, Bellingcat Tools|
|**Network & Source Traceability**|Trace network origins, domains, C2PA provenance|WhoisXML API, [Maltego CE](https://www.paterva.com/), RiskIQ, [C2PA](https://c2pa.org/)|
|**Cross-Modal Consistency**|Check if narrative matches across modalities|CrossCheck, SensityAI, Reality Defender|
|**Automation & Pipelines**|Automate via pipelines, ML models, SIEM/XDR integrations|Apache Tika, HuggingFace pipelines, Python, MISP, Sigma rules|

## Appendix B: Automation Snippets & Field Kit

### Image & Metadata

- **Extract metadata (all files in folder to CSV):**
    
    ```bash
    exiftool -csv -r folder/ > exif_report.csv
    ```
    
- **Strip metadata for sharing (privacy):**
    
    ```bash
    mat2 file.jpg
    ```
    

### Video Analysis

- **Extract 1 frame per second:**
    
    ```bash
    ffmpeg -i video.mp4 -vf fps=1 frames/out_%04d.jpg
    ```
    
- **Extract scene changes:**
    
    ```bash
    ffmpeg -i video.mp4 -filter:v "select='gt(scene,0.4)',showinfo" -vsync vfr scenes/out_%04d.jpg
    ```
    
- **Get video codec/container info:**
    
    ```bash
    mediainfo video.mp4
    ```
    

### Audio Analysis

- **Convert to WAV for spectrograms:**
    
    ```bash
    ffmpeg -i input.mp4 -vn -acodec pcm_s16le output.wav
    ```
    
- **Generate spectrogram (SoX):**
    
    ```bash
    sox output.wav -n spectrogram -o spectro.png
    ```
    

### Text Analysis

- **Detect AI-like text probability (DetectGPT):**
    
    ```python
    from detectgpt import DetectGPT
    model = DetectGPT()
    score = model.score_text("sample text")
    print(score)
    ```
    
- **Check perplexity with GPT-2 LM (HuggingFace):**
    
    ```python
    from transformers import GPT2LMHeadModel, GPT2TokenizerFast
    import torch
    
    model = GPT2LMHeadModel.from_pretrained("gpt2")
    tokenizer = GPT2TokenizerFast.from_pretrained("gpt2")
    
    text = "sample text"
    encodings = tokenizer(text, return_tensors="pt")
    max_length = model.config.n_positions
    stride = 512
    nlls = []
    for i in range(0, encodings.input_ids.size(1), stride):
        begin_loc = max(i + stride - max_length, 0)
        end_loc = i + stride
        trg_len = end_loc - i
        input_ids = encodings.input_ids[:, begin_loc:end_loc]
        target_ids = input_ids.clone()
        target_ids[:, :-trg_len] = -100
    
        with torch.no_grad():
            outputs = model(input_ids, labels=target_ids)
            nlls.append(outputs.loss * trg_len)
    
    ppl = torch.exp(torch.stack(nlls).sum() / end_loc)
    print(ppl.item())
    ```
    

### Networking & Provenance

- **WHOIS lookup (Linux):**
    
    ```bash
    whois example.com
    ```
    
- **Get SSL/TLS certificate info:**
    
    ```bash
    echo | openssl s_client -connect example.com:443 -servername example.com 2>/dev/null | openssl x509 -noout -dates -issuer -subject
    ```
    

### Workflow Helpers

- **Batch hash files in folder:**
    
    ```bash
    sha256sum * > hashes.txt
    ```
    
- **Create case log template (Markdown):**
    
    ```markdown
    # Case Log
    - Case ID:
    - Analyst:
    - Date/Time (TZ):
    - Source URL/ID:
    - File Hashes (SHA-256):
    - Media Type:
    - Claimed Context:
    - Tools & Versions:
    - Findings:
    - Indicators:
    - Probability Band:
    - Peer Reviewer:
    - Final Conclusion:
    ```
