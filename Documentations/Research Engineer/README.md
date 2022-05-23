Role: Research Engineer
=======================
Responsibilities:
-----------------
1. Utilize dataset toolkit to create datasets pipeline.
2.	Create AI/Deep Learning models that gain 0,9 in F1-score on detecting multiple classes of defects using object detection or image segmentation.
3.	Create model servings based on the respective models
4.	Utilize model toolkit to evaluate model performance and generate reports.
5.	Create research reports for future research decisions.

Task:
-----
1.	Discuss with the team to break down research tasks.
2.	Maintain current dataset using dataset toolkit.
3.	Train YOLO/darknet models.
4.	Studying other training environments such as mmdetection, detectron2, de-tr, U-Net, darknet.
5.	Create model serving implementations from each respective model.
6.	Generate reports.

Guidelines
----------
1. Creating Dataset Pipeline
   1. Dataset Preparation
      1. Port forwarding RKB1
         > ssh -L 8501:localhost:8501 -p 21021 ubuntu@202.158.77.42\
         > pass: adminRKB
      2. Akses browser
         > http://localhost:8501/
      3. Isi Data Info
         > Creator : nanang\
         > \
         > Description : data-apa_image-size_range-session-code_unique-grouping
      4. Pemilihan Atribut
         > Session Code \
            > Group 1 =  17, 19, 20, 21, 22, 23, 24, 25, 26, 27, 35, 36, 37, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53\
         > dimension = 500x500\
         > augment = no augment\
         > defect exist = positive and(or) negative\
         > Label version = 4\
         > Additional edit for class type
      5. > Load Labels
      6. Penyiapan Label
         > Include unlabeled images as negative data\
         > \
         > Generate COCO
      7. Limit number negative images
      8. Split Dataset dan catat jumlah gambar
         > Train: 8\
         > Valid: 1\
         > Test : 1
      9. Save coco json
         > bisa diubah nama file json
   2. Dataset Generation
      1. Choose Json File:
         > Train\
         > Valid\
         > Test 
      2. Choose Generated Dataset Format:
         > YOLO Detection\
         > Generate list of images text file\
         > Copy paths
      3. > Generate
   3. Model Registration
      1. Registration Type
         > Model Version
      2. Register New Model Version
         1. Model Version Name: Sesuai Nama Training
         2. ID of Model Source:
            > YOLO = 0c35df97-0e46-4769-8fdd-aededac08073
         3. Input nama file json training
         4. Input nama file json validation
         5. Input savedmodel directory
         6. Input training cfg path dalam savedmodel directory
      3. > Register
2. Training YOLO
   1. SSH RKB6
   2. > tmux a -t nanang
   3. Darknet directory:
      > /home/ubuntu/deo/workspace/textile/code/darknet\
      > training graph (nama sesuai dengan nama cfg)
   4. Dataset directory:
      > /nfs/ssd-1/textile/temp_dataset + nama_dataset
   5. SavedModel directory
      > /nfs/ssd-1/textile/ + nama_folder_training\
      > buat folder untuk saved model\
      > copy cfg training
   6. Folder for training
      > /home/ubuntu/deo/workspace/textile/code/darknet/backup + nama folder training\
      > config file, train.data, test.data, train.names
   7. Commands
      > ./darknet detector train [train.data path] [training cfg path] [pretrained path] -dont_show -map\
      > cek hasil dan update di dokumen
      > ./darknet detector map [test.data path] [training cfg path] [best weight in saved model path] -dont_show
   8. Setelah Training
      > Isi dokumen ini: https://docs.google.com/spreadsheets/d/1Q6b0-N-OU-gOj6r0O2G5goN5XSXlBRZNBwHCFkiZLfI/edit#gid=299872104