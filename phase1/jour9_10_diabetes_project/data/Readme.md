# Readme

## Objectif

Travailler sur la situation professionnelle simplonline de **création d'une PoC de détection du diabète**:   
https://simplonline.co/trainer-workspace/professional-situations/de69eece-0a6b-4c8a-8046-295742449506

Cette situation professionnelle est constituée de **6 briefs** sur simplonline:  
1. ML 1 - Extraction et préparation d'un dataset sur le diabète:  
https://simplonline.co/classrooms/7e241420-5d90-49b0-ac98-5cf0e55b4a0b/briefs/52fab772-6ba1-4cf0-860f-501fbd7aec44
2. ML 2 - Entraînement d'un modèle prédictif sur le diabète:  
https://simplonline.co/classrooms/7e241420-5d90-49b0-ac98-5cf0e55b4a0b/briefs/75b88d18-805f-451b-8115-649784f7f6e5
3. ML 3 - Création d'une API:  
https://simplonline.co/classrooms/7e241420-5d90-49b0-ac98-5cf0e55b4a0b/briefs/4423c035-6e54-447f-a2e2-0cd0a77f65c5
4. ML 4 - Application de scoring connectée à l'API:  
https://simplonline.co/classrooms/7e241420-5d90-49b0-ac98-5cf0e55b4a0b/briefs/979e30cc-43c8-4ead-8a52-1ce02cf0934c
5. ML 5 - Orchestration locale: API de scoring + Application:  
https://simplonline.co/classrooms/7e241420-5d90-49b0-ac98-5cf0e55b4a0b/briefs/4b883648-a470-4889-a5b9-5a223c357f7a
6. ML 6 - Mettre en ligne l'API + l'application sur le cloud:  
https://simplonline.co/classrooms/7e241420-5d90-49b0-ac98-5cf0e55b4a0b/briefs/658eb8c4-c993-433b-bebb-fdbccec8bfcc


## Dataset

Le dataset original provient des archives du UCI Machine Learning:  
https://archive.ics.uci.edu/dataset/529/early+stage+diabetes+risk+prediction+dataset

Ce dataset a été découpé en 2 parties:  
- `data/train_with_id.csv` pour l'apprentisage automatisé.  
- `data/test_without_class.csv` pour le test à l'aveugle du modèle.  

## Application d'évaluation du scoring  

Une application a été spécialement développée pour tester vos prédictions sur le set de test "caché":
https://0199c7ac-7e61-78e2-f901-9fc6570fdc50.share.connect.posit.cloud/  
