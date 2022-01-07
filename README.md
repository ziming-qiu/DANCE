# DANCE
The paper link: https://arxiv.org/pdf/2111.14741.pdf

The data set link: https://ieee-dataport.org/documents/bell-labs-robot-garage-dance-domain-adaptation-networks-camera-pose-estimation.
Inside the link, we have train folders with 100,000 labeled rendered images and	28411 unlabeled	real camera images.
We also	have the validation set	(1637 labeled real camera images) and test set (2104 labeled real camera images).

For rendering labeled synthetic images from the point cloud (render_training_images.zip):
render_training_images/data/data_collection/robot_lab_03_13_2020_000/dvc_pipelines/generate_random_poses_batches.sh generates random poses.

render_training_images/data/data_collection/robot_lab_03_13_2020_000/dvc_pipelines/render_random_images_in_batches.sh and render_training_images/data/data_collection/robot_lab_03_13_2020_000/dvc_pipelines/render_random_scene_coord_images_in_batches.sh use the generated random poses to render training images and corresponding scene coordicate labels.

Training and Testing (DANCE_training_testing_code.zip):

(1) DANCE_training_testing_code/histogram_match.ipynb to preprocess the training rendered images.

(2) going into DANCE_training_testing_code/cut folder, use the prepare_dataset.ipynb to prepare training data, run run_py_job.sbatch to train the cut based gan model.

(3) DANCE_training_testing_code/train_init_scr_cut.ipynb to train the final SCR model.

(4) DANCE_training_testing_code/test.ipynb

Another copy with trained model is in gitlab: https://gitlab.com/zq415/dance.
