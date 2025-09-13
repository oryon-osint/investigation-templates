# ✅ AI Detection Checklist

![Version](https://img.shields.io/badge/version-v1.0.0-blue)  
![Last Update](https://img.shields.io/badge/updated-2025--09--13-red)

A comprehensive and detailed checklist for detecting and analyzing AI-generated or manipulated media — including images, video, audio, and text. It is intended for OSINT investigators, journalists, digital forensic analysts, and security professionals who require structured, reliable verification procedures.

## 🖼️ Image & Visual Content Verification

-  **Anatomy & Object Integrity**
    
    - Inspect hands: count fingers, check proportions, examine nail shape and placement.
        
    - Examine eyes: look for mismatched irises, unnatural reflections, symmetry that is “too perfect.”
        
    - Inspect teeth: check if rendered as a uniform block, misaligned gum lines, or blurry interiors.
        
    - Inspect ears and earrings: check for asymmetry, distortions, or blending into hair/skin.
        
    - Check accessories (glasses, hats, jewelry) for warped edges, melting, or blending artifacts.
        
-  **Clothing & Fabrics**
    
    - Look for stitching errors, inconsistent textures, or repeating patterns.
        
    - Validate logos and printed text on clothing (AI often renders gibberish or blurred letters).
        
    - Check folds and shadows in fabric for natural consistency.
        
-  **Background Consistency**
    
    - Inspect signage and text in the background for legibility.
        
    - Identify warped objects (lamp posts, buildings, cars).
        
    - Check perspective lines: ensure vanishing points are consistent.
        
-  **Lighting & Shadows**
    
    - Ensure all shadows align with a single light source.
        
    - Validate intensity and direction of light on different objects.
        
    - Use [SunCalc](https://www.suncalc.org/) to validate time of day.
        
-  **Reflections**
    
    - Inspect mirrors, windows, and water surfaces.
        
    - Ensure reflected objects match reality (orientation, size, color).
        
-  **Technical Checks**
    
    - Run **reverse image search** on full image and cropped anomalies.
        
    - Perform **Error Level Analysis (ELA)** via [Forensically](https://29a.ch/photo-forensics/).
        
    - Inspect for cloning or copy-paste elements.
        
    - Review **EXIF metadata** using [ExifTool](https://exiftool.org/).
        
    - Validate GPS and timestamps against claimed context.
        

## 🎥 Video Verification

-  **Frame-by-Frame Analysis**
    
    - Scrub video frame by frame for inconsistencies.
        
    - Check lips vs. phonemes for sync accuracy.
        
    - Look for flickering artifacts or blending errors.
        
-  **Motion & Blur**
    
    - Validate natural motion blur; AI often generates sharp unnatural edges during motion.
        
    - Look for “halo” effects or ghosting in moving objects.
        
-  **Context Checks**
    
    - Verify landmarks, signs, and clothing seasonality.
        
    - Cross-check weather with [Meteostat](https://meteostat.net/) or [OGIMET](https://www.ogimet.com/).
        
    - Use [SunCalc](https://www.suncalc.org/) for shadow analysis.
        
-  **Technical Tools**
    
    - Extract thumbnails and keyframes with [InVID](https://www.invid-project.eu/tools-and-services/invid-verification-plugin/).
        
    - Run reverse video searches.
        
    - Analyze encoding for unusual compression signatures.
        
-  **AI Detection**
    
    - Run frames through [SensityAI](https://sensity.ai/) or Reality Defender.
        
    - Apply forensic CNNs like FaceForensics++.
        

## 🔊 Audio Verification

-  **Listening Checks**
    
    - Identify robotic cadence, flat intonation, or overly clean delivery.
        
    - Check for missing human sounds (breathing, mouth clicks, filler words).
        
    - Detect looping or repetitive background noise.
        
-  **Spectrogram Analysis**
    
    - Generate spectrograms in [Audacity](https://www.audacityteam.org/) or [Praat](https://www.fon.hum.uva.nl/praat/).
        
    - Look for:
        
        - Clean unnatural high frequencies.
            
        - Banding artifacts.
            
        - Missing natural harmonics.
            
-  **Environmental Verification**
    
    - Validate background sounds (birds, traffic, wind) against claimed setting.
        
    - Compare ambient audio with expected acoustics (e.g., indoor echo vs. outdoor open field).
        
-  **Technical Tools**
    
    - Run AI voice detection with Deepware Scanner or Intel FakeCatcher.
        
    - Compare with known samples of the speaker.
        
    - Analyze jitter/shimmer metrics in Praat.
        

## 📝 Textual Verification

-  **Linguistic Checks**
    
    - Identify repetitive scaffolding (e.g., “In conclusion, …”).
        
    - Look for vague or generic phrasing without specifics.
        
    - Check for fabricated citations, URLs, or ISBNs.
        
-  **Factual Validation**
    
    - Spot-check quotes and references against primary sources.
        
    - Cross-verify dates, events, and names in OSINT databases.
        
-  **Technical Tools**
    
    - Run [GLTR](http://gltr.io/) or [DetectGPT](https://github.com/eric-mitchell/detect-gpt).
        
    - Perform stylometric comparison with JStylo.
        
    - Use HuggingFace AI detection models for second opinion.
        

## 🌍 Contextual & Environmental Consistency

-  Validate location using Google Earth and Street View.
    
-  Cross-check building architecture with regional styles.
    
-  Verify vegetation/season (trees in bloom vs. claimed season).
    
-  Validate weather data with [Meteostat](https://meteostat.net/) or [OGIMET](https://www.ogimet.com/).
    
-  Check holidays, political events, or known gatherings on claimed date.
    
-  Match crowd size against known venue capacity.
    
## 📊 Metadata & Technical Fingerprints

-  **EXIF Analysis**
    
    - Extract with [ExifTool](https://exiftool.org/).
        
    - Look for missing or improbable fields.
        
    - Detect editing software tags (Stable Diffusion, MidJourney, Photoshop).
        
-  **Compression & Encoding**
    
    - Validate JPEG quantization tables.
        
    - Compare video codecs against known device profiles.
        
-  **Sensor Noise & PRNU**
    
    - Run [Noiseprint](https://github.com/isi-vista/noiseprint) for sensor fingerprinting.
        
    - Compare with known authentic samples.
        
-  **Provenance Checks**
    
    - Check for C2PA metadata.
        
    - Validate Adobe Content Credentials.
        
    - Run Google SynthID watermark checks if available.
        
## 🤝 Peer Review & Validation

-  Share findings with a second analyst for independent validation.
    
-  Compare across multiple tools and detection methods.
    
-  Store SHA256 and MD5 hashes of original files for integrity.
    
-  Maintain chain of custody logs for evidentiary purposes.
    
-  Document all anomalies with annotated screenshots.
    
-  Record all commands, queries, and tools used for auditability.
    
## 🛠️ Quick Access Tools

|Tool|Type|Purpose|
|---|---|---|
|[Forensically](https://29a.ch/photo-forensics/)|Image forensics|Error level analysis, clone detection, metadata review|
|[InVID Plugin](https://www.invid-project.eu/tools-and-services/invid-verification-plugin/)|Video verification|Extract thumbnails, reverse video search, metadata analysis|
|[ExifTool](https://exiftool.org/)|Metadata extraction|Inspect and validate EXIF and file metadata|
|[GLTR](http://gltr.io/)|Text analysis|Detect statistical patterns in AI-generated text|
|[DetectGPT](https://github.com/eric-mitchell/detect-gpt)|Text analysis|Identify likely AI-generated passages|
|[Noiseprint](https://github.com/isi-vista/noiseprint)|Image forensics|Sensor fingerprinting and camera source validation|
|[Audacity](https://www.audacityteam.org/)|Audio analysis|Waveform and spectrogram inspection|
|[Praat](https://www.fon.hum.uva.nl/praat/)|Audio forensics|Acoustic analysis of speech and voice patterns|
|[Meteostat](https://meteostat.net/)|Contextual data|Historical weather validation|
|[SunCalc](https://www.suncalc.org/)|Contextual analysis|Validate shadows and sun positions by time and place|
|[SensityAI](https://sensity.ai/)|AI detection|Deepfake and synthetic media detection services|


### 🔖 Credits

Maintained by **Oryon** +**[OSINT360 GPT](https://tntpp9.short.gy/osint360-gpt)**.  
This document is part of the **Cyber Intelligence Toolkit** project.  
