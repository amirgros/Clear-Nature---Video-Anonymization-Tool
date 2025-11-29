# Clear Nature - Video Anonymization

# 🎥 Auto-Erasing People from Videos

A computer vision tool that automatically detects and erases people (and their shadows) from video footage, replacing them with a plausible background. This project was developed as part of a course at the **Technion - Israel Institute of Technology**.

## 📝 Project Summary

This tool offers an automated pipeline for erasing people from videos. Unlike standard inpainting tools that require manual masking, this project automates the entire process:

1.  **Frame Splitting:** The input video is broken down into individual frames.
2.  **Person Detection (YOLOv8):** A fine-tuned YOLOv8 model detects people and generates precise segmentation masks.
3.  **Shadow Detection:** A custom shadow detection module identifies and adds shadows to the mask to ensure clean removal.
4.  **Inpainting (Eddy):** The "Eddy" algorithm uses information from neighboring frames (temporal consistency) to fill in the erased area seamlessly.
5.  **Reassembly:** The processed frames are stitched back into a final clean video.

## 🎞️ Demo

[Demo_Video](https://github.com/user-attachments/assets/6cb5672f-31c4-4cb4-a320-459997e83b21)


https://github.com/user-attachments/assets/ef10d451-43cb-47ce-87f2-f936d4269fb9



https://github.com/user-attachments/assets/e7bde998-49db-4500-95ee-d3fc87137042



## 🚀 How to Use

The project is designed to run easily via Google Colab.

1.  **Open the Notebook:**
    Open the `Clear_Nature_Video.ipynb` in Google Colab.

2.  **Upload Required Files:**
    Connect to the runtime and upload the following files to the root `/content` folder:
    * `shadow_model_full.pth` (The weights for the shadow detection module), can be found in [Project_Drive](https://drive.google.com/drive/folders/1GgvzRYu2pRWxGRhZXLl3C_LUwN3P97HK?usp=sharing).
    * `your_video.mp4` (The video/s you want to process).

3.  **Run the Pipeline:**
    Execute all cells in the notebook. The script will automatically:
    * Extract frames.
    * Generate masks for people and shadows.
    * Run the inpainting process.
    Note that installation cell (first cell) may take a while to run (up to 45 min in some cases).

4.  **Get Results:**
    A new folder `/content/results/[video_name]` will be created. Your final processed video and intermediate masks will be saved there.
    

## 🎓 Credits & Acknowledgments

**Creators:**
* Amir Grosssman
* Maya Attia
Both from the Andrew and Erna Viterbi Faculty of Electrical and Computer Engineering Technion.

**Lab & Supervision:**
This project was carried out in the **Vision and Image Sciences Laboratory (VISL)** at the Technion, Faculty of Electrical & Computer Engineering.
Special thanks to the lab staff and the Technion for the resources and guidance provided during this project.

* **Supervisor:** Johanan Erez
* **Lab:** [VISL - Vision and Image Sciences Laboratory](https://visl.technion.ac.il/)

**E2FGVI Inpaint Tool:**
Both for the article "Towards An End-to-End Framework for Flow-Guided Video Inpainting" and Repo at [MCG-NKU/E2FGVI](https://github.com/MCG-NKU/E2FGVI).


For more information, contact us at:
* amirgrossman@campus.technion.ac.il
* maya.attia@campus.technion.ac.il
---
*Created for Project A, Spring 2025.*
