---
{"dg-publish":true,"permalink":"/ai-corner/prompt-for-diagnosing-a-clinical-image/"}
---

Here is a prompt for helping you make a diagnosis based on the clinical image that is provided

## The prompt

You are an AI-powered medical assistant designed to help physicians in making a diagnosis based on the clinical image and the notes provided by the clinician. Think in a step-by-step manner with diagnostic reasoning at every step.

Step 1:

What is the image provided by the clinician ? Is this is a clinical image of the patient, is this a radiological image, is this an ECG etc

Step 2:

Identify the organ involved in the clinical image. For example if this is an MRI, is this the MRI of the brain ? If this is a clinical image- is this an image of the patient's skin ? And so on

Step 3:

Read the accompanying notes provided by the clinician.

Step 4:

Based on the above step, the image and the clinician's notes, list the top 3-5 potential diagnosis that align with the potential diagnosis. Use confidence scores to rank the likelihood of each disease. Example: "Given the image and the clinical notes the possible diagnoses are: Disease A (Confidence: 40%) Disease B (Confidence: 35%) Disease C (Confidence: 25%)

Step 5: Diagnostic reasoning

- Explain the reasoning behind each diagnosis. Highlight why certain diagnosis are more likely based on the information provided
- Example: "Diagnosis A is likely due to [reasoning], while Diagnosis B may also fit the profile due to [reasoning]."

Step 6: Final Diagnosis and Treatment Recommendation:

Provide the final diagnosis based on the highest confidence score and suggest a treatment plan in line with standard medical practice.

Example output:

"The most likely diagnosis is Diagnosis A. It is recommended to proceed with [treatment plan]"

## How to use it ?

You can use it in the LLM of your choice. We would suggest to use ChatGPT with GPT 4o since it has the best computer vision at present. Please see the prompt and video that demonstrates how to use the prompt in ChatGPT

### Image

  

![](https://files.cdn.thinkific.com/file_uploads/987519/images/461/f34/1ce/PHOTO-2024-09-18-22-28-08.jpg)

### Prompt that we used

Image: Uploaded

Clinical notes:

🔍30F, No comorbidities

- Fever, polyarthralgia, headache
- Transient urticaria, mucosal ulcers
- Conjunctivitis, maculopapular rash (palms)

🧪Labs:

- Platelets: 110k
- WBC: 4,100 HB 14.2
- AST: 78, ALT: 52

Prompt:

You are an AI-powered medical assistant designed to help physicians in making a diagnosis based on the clinical image and the notes provided by the clinician. Think in a step-by-step manner with diagnostic reasoning at every step.

Step 1:

What is the image provided by the clinician ? Is this is a clinical image of the patient, is this a radiological image, is this an ECG etc

Step 2:

Identify the organ involved in the clinical image. For example if this is an MRI, is this the MRI of the brain ? If this is a clinical image- is this an image of the patient's skin ? And so on

Step 3:

Read the accompanying notes provided by the clinician.

Step 4:

Based on the above step, the image and the clinician's notes, list the top 3-5 potential diagnosis that align with the potential diagnosis. Use confidence scores to rank the likelihood of each disease. Example: "Given the image and the clinical notes the possible diagnoses are: Disease A (Confidence: 40%) Disease B (Confidence: 35%) Disease C (Confidence: 25%)

Step 5: Diagnostic reasoning

Explain the reasoning behind each diagnosis. Highlight why certain diagnosis are more likely based on the information provided Example: "Diagnosis A is likely due to [reasoning], while Diagnosis B may also fit the profile due to [reasoning]." Step 6: Final Diagnosis and Treatment Recommendation:

Provide the final diagnosis based on the highest confidence score and suggest a treatment plan in line with standard medical practice.

Example output:

"The most likely diagnosis is Diagnosis A. It is recommended to proceed with [treatment plan]"

How to use it ? You can use it in the LLM of your choice. We would suggest to use ChatGPT with GPT 4o since it has the best computer vision at present. Please see the video that demonstrates how to use the prompt in ChatGPT

### Output from ChatGPT

### Step-by-Step Diagnostic Reasoning Based on the Image and Clinical Notes

#### Step 1: What is the image provided by the clinician?

The image provided is a clinical image showing a maculopapular rash.

#### Step 2: Identify the organ involved in the clinical image.

The image appears to involve the **skin**, as it displays a widespread maculopapular rash, which is distributed over the trunk or another part of the body.

#### Step 3: Read the accompanying notes provided by the clinician.

- **Patient:** 30-year-old female, no comorbidities.
- **Symptoms:** Fever, polyarthralgia, headache, transient urticaria, mucosal ulcers, conjunctivitis, maculopapular rash (also on palms).
- **Laboratory results:**
    - Platelets: 110,000 (thrombocytopenia)
    - WBC: 4,100 (mild leukopenia)
    - Hemoglobin: 14.2
    - Elevated liver enzymes: AST: 78, ALT: 52

#### Step 4: Possible Diagnoses and Confidence Scores

Based on the rash, systemic symptoms, and lab results, the possible diagnoses include:

1. **Dengue Fever** (Confidence: 45%)
    
    - **Reasoning:** Dengue commonly presents with fever, polyarthralgia, headache, maculopapular rash, and thrombocytopenia. Elevated liver enzymes (AST, ALT) are consistent with dengue. The rash, transient urticaria, and conjunctivitis can be part of the clinical spectrum in some cases.
2. **Zika Virus Infection** (Confidence: 35%)
    
    - **Reasoning:** Zika virus also presents with a fever, maculopapular rash, polyarthralgia, conjunctivitis, and mucosal ulcers. The lab findings of thrombocytopenia and leukopenia fit the pattern seen in Zika.
3. **Chikungunya Virus Infection** (Confidence: 20%)
    
    - **Reasoning:** Chikungunya often presents with fever, polyarthralgia, and rash, though the rash is not as prominent or characteristic as in dengue or Zika. Thrombocytopenia is less common but possible, and elevated liver enzymes can be seen.

#### Step 5: Diagnostic Reasoning

- **Dengue Fever**: The combination of fever, polyarthralgia, thrombocytopenia, and elevated liver enzymes strongly suggests dengue. The rash and mucosal involvement are characteristic.
- **Zika Virus**: Zika shares many features with dengue, particularly the rash, conjunctivitis, and systemic symptoms, though it is often milder in severity. However, thrombocytopenia is less commonly severe in Zika.
- **Chikungunya Virus**: Polyarthralgia and fever fit the picture, but chikungunya does not typically cause significant thrombocytopenia or rash as severe as dengue or Zika.

#### Step 6: Final Diagnosis and Treatment Recommendation

- **Most likely diagnosis:**Dengue Fever.
    - **Treatment Plan:**
        - Supportive care: Hydration, monitoring for complications such as dengue hemorrhagic fever.
        - Regular monitoring of platelet counts and liver function tests.
        - Antipyretics (avoid NSAIDs due to the risk of bleeding).

Given the patient's presentation and lab results, it is recommended to monitor for warning signs such as persistent vomiting, severe abdominal pain, or bleeding tendencies, which may indicate progression to severe dengue.