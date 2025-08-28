[![GSoC](https://github.com/user-attachments/assets/48ee60ec-010e-41f7-a3cf-0474e4f08ed5)](https://summerofcode.withgoogle.com/)  [![Sugar Labs](https://github.com/user-attachments/assets/70ad23bd-757d-4ab5-8229-571434c047f1)](https://www.sugarlabs.org/)

# Google Summer of Code 2025 – Final Report  
**Organization:** [Sugar Labs](https://sugarlabs.org)             
**Project:** Sugarizer Human Activity Pack           

**Contributor:** Aditya Kumar Singh         
**GitHub:** [AdityaKrSingh26](https://github.com/AdityaKrSingh26)        
**Email:** adityakrsingh2604@gmail.com      
**LinkedIn:** [Aditya Kumar Singh](https://www.linkedin.com/in/aditya-kumar-singh)            
 
**Mentors:** [Lionel Laské](https://github.com/llaske)            
**Co-mentor:** [Samarth Bagga](https://github.com/SamarthBagga)           

---

## **Project Overview**
The objective of this project was to **enhance the 3D Human Body Activity** and **create a new Stickman Animation Activity** for Sugarizer, an open-source learning platform by Sugar Labs. These activities aim to make **learning anatomy and animation interactive, accessible, and collaborative**, especially for low-resource environments.

- **3D Human Body Activity**:  
  An interactive 3D anatomy explorer that allows toggling between different body systems, painting and labeling structures, and multiplayer learning with quiz-based **Doctor Mode**.

- **Stickman Animation Activity**:  
  A frame-based animation editor with onion-skinning, drag-and-drop joint manipulation, templates, and **AI-assisted pose generation** using PoseNet, enabling students to create animations intuitively.

Both activities are optimized for **Sugarizer** and designed for **offline-first usage** on low-power devices.

---

## **Features Implemented**

### **1. 3D Human Body Activity Enhancements**
- **Multi-layer anatomical system integration:** Added skeletal, muscular, and organ systems with **dynamic layer toggling**.
- **Doctor Mode (Shared Multiplayer Mode):** Real-time collaborative quiz feature over Sugar Presence API.
- **Paint Mode & Learn Mode:** Users can select, color, and label parts with educational descriptions.
- **Tour Mode:** Guided navigation across anatomical systems for structured learning.
- **Localization:** Added multi-language support using **l10n.js** (English & French implemented).
- **Performance Optimization:** Preprocessed models using Blender (polygon reduction, mesh optimization) to ensure smooth rendering on low-resource devices.
- **UI Previews:**      
   <img width="640" height="334" alt="humanbody1" src="https://github.com/user-attachments/assets/3d19b17d-8120-479c-b9a1-dbbe9f5bbc4e" />
   <img width="640" height="334" alt="humanbody2" src="https://github.com/user-attachments/assets/25e03fe8-1954-47e3-bd0d-a664ea3e1f0e" />
   <img width="640" height="334" alt="humanbody3" src="https://github.com/user-attachments/assets/6511a671-12f7-455d-9dc4-1f246a3734e7" />
   <img width="640" height="334" alt="humanbody-shared" src="https://github.com/user-attachments/assets/7ea426d6-2ac9-4ea4-b466-ed157dd99e2e" />


### **2. Stickman Animation Activity**
- **Joint-Based Stickman Editor:** Users can click and drag joints to create custom poses.
- **Keyframe Animation with Timeline:** Added frame sequencing and thumbnail previews.
- **Onion Skinning:** Semi-transparent previews for previous/next frames for smoother animation.
- **Templates & Presets:** Preloaded actions like running, jumping, and dancing.
- **AI-Pose Detection:** Integrated TensorFlow.js + PoseNet to generate stick figure poses from uploaded images.
- **Export Feature:** Export animations as **WebM** videos using MediaRecorder API.
- **Shared Mode:** Real-time collaboration using Sugarizer Presence API.
- **UI Previews:**         
   <img width="640" height="334" alt="stickmen-ui" src="https://github.com/user-attachments/assets/33156227-ccfa-49b2-9a1c-0f8756c189bf" />
   <img width="640" height="334" alt="image" src="https://github.com/user-attachments/assets/a941ac73-ea6c-4c96-af50-3e6bd92cc27f" />
   <img width="640" height="334" alt="image" src="https://github.com/user-attachments/assets/ded919d5-15db-4696-8278-261002bd0bee" />


---

## **Technologies Used**
- **Languages:** JavaScript (ES6), HTML5, CSS3  
- **Frameworks & Libraries:**  
  - **Three.js** (3D rendering)  
  - **TensorFlow.js & PoseNet** (Pose detection for Stickman)  
  - **Sugar-Web APIs** (Activity lifecycle, storage, networking)  
- **Networking:** WebSockets (via Sugar presence API)  
- **Graphics:** WebGL & Canvas API  
- **Internationalization:** l10n.js  

---

## **Architecture & Design Highlights**
### **Human Body Activity**
- **Rendering Layer:** Three.js + GLTFLoader for loading models.
- **Modes:** Paint, Learn, Tour, Doctor (Quiz).
- **Networking:** Real-time sync for shared sessions via Presence API.
- **Persistence:** State saving using Sugar Journal.

### **Stickman Activity**
- **Data Model:** Base + Delta frames for optimized animation storage.
- **Constraints:** Maintains anatomical proportions when dragging joints.
- **Export:** Uses frame-by-frame rendering to generate video output.

---

## **Challenges Faced**
- **3D Asset Optimization:** Original anatomical models were too heavy for low-end devices; solved by Blender preprocessing.
- **Pose Detection Accuracy:** Fine-tuned joint mapping for PoseNet integration to ensure correct stick figure generation.
- **Multiplayer Sync:** Implemented throttled updates and state normalization to handle real-time collaboration without lag.

---


## **Repository Links**
- **Repository:** [GitHub Link](https://github.com/llaske/sugarizer)
- **Human Body Activity - Branch:** [GitHub Link](https://github.com/AdityaKrSingh26/sugarizer/tree/dev-3d)
- **Stickman Animation Activity - Branch:** [GitHub Link](https://github.com/AdityaKrSingh26/sugarizer/tree/feature/aditya-stickman)
- **Pull Requests:**
    - Human Body Activity PR: [#1794](https://github.com/llaske/sugarizer/pull/1794), [#1796](https://github.com/llaske/sugarizer/pull/1796), [#1798](https://github.com/llaske/sugarizer/pull/1798), [#1800](https://github.com/llaske/sugarizer/pull/1800), [#1801](https://github.com/llaske/sugarizer/pull/1801), [#1802](https://github.com/llaske/sugarizer/pull/1802)     
    - Stickman Animation Activity PR: [#1799](https://github.com/llaske/sugarizer/pull/1799)        


---

### Contributions Prior to GSoC

| S.No | Issue Description                                                                 | Issue Link                                                                                      | PR Link                                                                                         | Status       |
|------|-----------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|-------------|
| 1    | Activity Description opening downwards in Journal                                | [#1407](https://github.com/llaske/sugarizer/issues/1407)                                      | [#1667](https://github.com/llaske/sugarizer/pull/1667)                                     | Merged      |
| 2    | Listview Popup increasing page length and opening downwards for lower icons      | [#1674](https://github.com/llaske/sugarizer/issues/1674)                                      | [#1675](https://github.com/llaske/sugarizer/pull/1675)                                     | Merged      |
| 3    | Vertical bar broken in Chart/Gears activities on Windows                         | [#1646](https://github.com/llaske/sugarizer/issues/1646)                                      | [#1673](https://github.com/llaske/sugarizer/pull/1673)                                     | Merged      |
| 4    | [v2] Listview lines spacing/padding is wrong                                     | [#1650](https://github.com/llaske/sugarizer/issues/1650)                                      | [#1669](https://github.com/llaske/sugarizer/pull/1669)                                     | Merged      |
| 5    | In the activity of food chain, the picture of frog shows incomplete              | [#1191](https://github.com/llaske/sugarizer/issues/1191)                                      | [#1681](https://github.com/llaske/sugarizer/pull/1681)                                     | Merged      |
| 6    | Pressing start button in ColorMyWorld activity immediately shows Congratulations | [#1691](https://github.com/llaske/sugarizer/issues/1691)                                      | [#1692](https://github.com/llaske/sugarizer/pull/1692)                                     | Merged      |
| 7    | Bug: Error loading Etoys activity                                                | [#1717](https://github.com/llaske/sugarizer/issues/1717)                                      | [#1718](https://github.com/llaske/sugarizer/pull/1718)                                     | Merged      |
| 8    | Bug: BlockRain Activity Game Over Logic Fails When Side Columns Are Full        | [#1739](https://github.com/llaske/sugarizer/issues/1739)                                      | [#1741](https://github.com/llaske/sugarizer/pull/1741)                                     | Merged      |
| 9    | Ability to resize images in Fototoon                                            | [#1551](https://github.com/llaske/sugarizer/issues/1551)                                      | [#1698](https://github.com/llaske/sugarizer/pull/1698)                                     | Draft |

---

### Weekly Blog Summary

| Week    | Blog Link                                                                                                           | Blog Excerpt                                                                                  |
|---------|--------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------|
| 1  | [Week 1 Blog](https://www.sugarlabs.org/news/developer-news/2025-05-28-gsoc-25-AdityaKrSingh26-week01)            | Refining human anatomy models and improving Sugarizer’s 3D Human Activity    |
| 2  | [Week 2 Blog](https://www.sugarlabs.org/news/developer-news/2025-05-29-gsoc-25-AdityaKrSingh26-week02)            | Merging anatomical models and enhancing Sugarizer’s Human Body Activity            |
| 3  | [Week 3 Blog](https://www.sugarlabs.org/news/developer-news/2025-06-02-gsoc-25-AdityaKrSingh26-week03)            | Organ integration, anatomical bisection, and open-source attributions in Sugarizer's Human Body Activity   |
| 4  | [Week 4 Blog](https://www.sugarlabs.org/news/developer-news/2025-06-10-gsoc-25-AdityaKrSingh26-week04)            | localization for 3D Human Activity in Sugarizer, palette switcher, and skeletal improvements.                            |
| 5  | [Week 5 Blog](https://www.sugarlabs.org/news/developer-news/2025-06-17-gsoc-25-AdityaKrSingh26-week05)            | UI improvements, model fixes, skeletal updates, and continued localization work for the 3D Human Activity in Sugarizer.                                     |
| 6  | [Week 6 Blog](https://www.sugarlabs.org/news/developer-news/2025-06-20-gsoc-25-AdityaKrSingh26-week06)            | Model optimizations, onboarding tutorial, adding json for body parts, and Shared mode enhancements in Paint Mode for the 3D Human Activity in Sugarizer.    |
| 7  | [Week 7 Blog](https://www.sugarlabs.org/news/developer-news/2025-06-30-gsoc-25-AdityaKrSingh26-week07)            | Enhanced shared mode synchronization for Tour and Doctor activities, improved scoring visualization, and camera state persistence in the 3D Human Activity.      |
| 8  | [Week 8 Blog](https://www.sugarlabs.org/news/developer-news/2025-07-08-gsoc-25-AdityaKrSingh26-week08)            | Resolved key issues in shared Paint & Tour workflows, introduced a real-time XO-icon leaderboard in Doctor mode, and bootstrapped the Stickman activity scaffold.             |
| 9  | [Week 9 Blog](https://www.sugarlabs.org/news/developer-news/2025-07-15-gsoc-25-AdityaKrSingh26-week09)            | Enhanced collaboration in Human Body activity by refining Paint and Tour interactions, improved UX in Doctor mode, and launched key features in Stickman like frame handling and animation controls.                      |
| 10 | [Week 10 Blog](https://www.sugarlabs.org/news/developer-news/2025-07-20-gsoc-25-AdityaKrSingh26-week010)          | Improved UX and syncing in Human Body activity, enhanced Stickman dashboard visuals, redesigned proportions, and implemented Journal save & multi-stickman support.              |
| 11 | [Week 11 Blog](https://www.sugarlabs.org/news/developer-news/2025-07-27-gsoc-25-AdityaKrSingh26-week011)          | Polished multi-stickman support with per-frame rendering, single-shadow enforcement, per-joint visibility, and safe delete flow. Also increased stickman size for better canvas presence.             |
| 12 | [Week 12 Blog](https://www.sugarlabs.org/news/developer-news/2025-08-04-gsoc-25-AdityaKrSingh26-week12)           | Enhanced user experience with image export functionality for Human Body activity, improved stickman visual design, comprehensive localization support, and interactive tutorial system implementation.     |
| 13 | [Week 13 Blog](https://www.sugarlabs.org/news/developer-news/2025-08-07-gsoc-25-AdityaKrSingh26-week13)           | Fixed critical model switching bugs in Human Body activity, enhanced Stickman animation with individual frame management, transitioned to relative positioning, and began implementing shared mode functionality.             |
| 14 | [Week 14 Blog](https://www.sugarlabs.org/news/developer-news/2025-08-17-gsoc-25-AdityaKrSingh26-week14)           | Enhanced shared mode ownership & visibility for Stickman, added Journal import functionality for saved stickmen, and export-to-video integration with Journal storage.          |
| 15 | [Week 15 Blog](https://www.sugarlabs.org/news/developer-news/2025-08-25-gsoc-25-AdityaKrSingh26-week15)           | Enhanced shared mode position handling, optimized export-to-video with bounding box stabilization, and introduced AI-based stickman import from video.          |

**All Blogs:** [Author Page](https://www.sugarlabs.org/authors/aditya-singh)


---
## **Acknowledgments**
Special thanks to my mentors **Lionel Laské** and **Samarth Bagga**, and the **Sugar Labs community** for their guidance and support. This project was an incredible journey of learning and contributing to open-source education.
