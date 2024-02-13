# Machine-Learning-Projects
This repository serves as a record of my practice ML projects. It includes notebooks and solutions for both structutred data and unstructured data projects. Each type of project is organized within its respective folder, complete with accompanying documentation and any necessary resources.

## 📄 Projects List

### [Structuted data projects](https://github.com/Rishikesh-Jadhav/CMSC848F-3D-Vision/tree/main/Project1): Rendering with Pytorch3D

- **Learnings from Project 1**:

  1. __Rendering First Mesh:__ Acquired a basic understanding of mesh rendering using PyTorch3D.

  2. __Practicing with Cameras:__ Created 360-degree gifs and set camera viewpoints for rendering.

  3. __Re-creating the Dolly Zoom:__ Successfully implemented the Dolly Zoom effect in PyTorch3D.
     <img src="reviews_and_presentations/outputs/a1_dolly_zoom.png" alt="dolly zoom" width="400"/>

  4. __Practicing with Meshes:__ Created and rendered 3D shapes such as a tetrahedron and a cube.

  5. __Re-texturing a Mesh:__ Changed mesh colors based on vertex positions.

  6. __Camera Transformations:__  Implemented camera pose transformations for rendering.

  7. __Rendering Generic 3D Representations:__ Rendered point clouds and constructed them from RGB-D images. Parametrically generated and rendered point clouds.
     <img src="reviews_and_presentations/outputs/a1_tree12_pc.png" alt="Tree Point Clouds" width="800"/>
     
  8. __Implicit Surfaces:__ Utilized implicit functions to define surfaces and converted them to meshes. Rendered a torus mesh with an implicit function and discussed mesh vs. point cloud rendering trade-offs.  
     <img src="reviews_and_presentations/outputs/a1_torus.png" alt="Torus" width="450"/> <img src="reviews_and_presentations/outputs/a1_torus_imp.png" alt="Implicit Torus" width="330"/>

  ### [Project 2](https://github.com/Rishikesh-Jadhav/CMSC848F-3D-Vision/tree/main/Project2):  Single View to 3D

- **Learnings from Project 2**:
 
  1. **Exploring Loss Functions:**
     - *Fitting a Voxel Grid:* Understood and implemented binary cross-entropy loss for regressing to 3D binary voxel grids.
       <img src="reviews_and_presentations/outputs/a2_voxel_grid.png" alt="dolly zoom" width="70%">
     - *Fitting a Point Cloud:* Successfully implemented Chamfer loss for fitting 3D point clouds and wrote custom code for this purpose.
       <img src="reviews_and_presentations/outputs/a2_point_cloud.png" alt="dolly zoom" width="70%">
     - *Fitting a Mesh:* Defined a smoothing loss for fitting a 3D mesh, utilizing pre-defined losses in the PyTorch library.
       <img src="reviews_and_presentations/outputs/a2_mesh.png" alt="dolly zoom" width=70%">
  
  2. **Reconstructing 3D from Single View:**
     - *Designed an Image to Voxel Grid Model:* Created a neural network to decode binary voxel grids, possibly modifying the provided decoder, and trained the single-view to voxel grid pipeline.
     - *Developed an Image to Point Cloud Model:* Designed a neural network to decode point clouds, similar to voxel grid, and trained the single-view to point cloud pipeline.
       <img src="reviews_and_presentations/outputs/a2_rgb2pc.png" alt="dolly zoom" width="70%">
     - *Defined an Image to Mesh Model:* Developed a neural network to decode meshes, modified the provided decoder, and trained the single-view to mesh pipeline. Experimented with different mesh initializations.
       <img src="reviews_and_presentations/outputs/a2_rgb2mesh.png" alt="dolly zoom" width="70%">
     - *Conducted Quantitative Comparisons:* Compared F1 scores of 3D reconstruction for meshes, point clouds, and voxel grids and justified the comparison with an intuitive explanation.
     - *Analyzed Effects of Hyperparameter Variations:* Investigated the impact of varying hyperparameters, such as n_points, vox_size, w_chamfer, or initial mesh, on the model's performance.
     - *Interpreted My Model:* Created insightful visualizations to understand what the learned model does and gained insights into its behavior. This included visualizing feature maps and encoder information.
       <img src="reviews_and_presentations/outputs/a2_last_layerof_encoder.png" alt="dolly zoom" width="50%">


These learnings encompass a wide range of topics related to 3D reconstruction from single-view RGB input, loss functions, neural network design, and hyperparameter tuning. Additionally, they include the use of PyTorch and PyTorch3D for   implementing these concepts.  
    
### [Project 3](https://github.com/Rishikesh-Jadhav/CMSC848F-3D-Vision/tree/main/Project3): Volume Rendering and Neural Radiance Fields

- **Learnings from Project 3**:

  1. **Differentiable Volume Rendering:**

      - **Ray Sampling:** Learned how to generate world space rays from camera positions and pixel coordinates using PyTorch3D.

      - **Point Sampling:** Implemented a stratified sampler to generate sample points along each ray, taking into account near and far distances. Explored visualization of sample points.

      - **Volume Rendering:** Implemented a volume renderer that evaluates a volume function at each sample point along a ray, aggregates these evaluations, and renders color and depth information. Explored volume density and color computations based on the emission-absorption model.

  2. **Optimizing a Basic Implicit Volume:**

      - **Random Ray Sampling:** Implemented random ray sampling to optimize the position and side lengths of a 3D box. Explored the concept of training on a subset of rays to save memory.

      - **Loss and Training:** Replaced loss functions with Mean Squared Error (MSE) between predicted colors and ground truth colors (rgb_gt). Conducted training and reported the center and side lengths of the optimized box.

      - **Visualization:** Created a spiral rendering of the optimized volume and compared it with a reference gif.

  3. **Optimizing a Neural Radiance Field (NeRF):**
      
      - **NeRF Implementation:** Implemented an implicit volume as a Multi-Layer Perceptron (MLP) to map 3D positions to volume density and color. Utilized ReLU activation for density and Sigmoid activation for color. Explored the use of Positional Encoding for improved quality.

      - **Loss and Training:** Wrote the loss function for training the NeRF model on RGB images. Explored data loading, training, and checkpointing. Trained NeRF on the lego bulldozer dataset.

      - **Visualization:** Trained a NeRF on a specific dataset and created a spiral rendering of the optimized volume. Reported the results and compared them to reference visuals.
        <img src="reviews_and_presentations/outputs/a3_nerf_optim.png" width="70%">
        
These learnings encompass various aspects of differentiable volume rendering, 3D optimization, and the implementation of Neural Radiance Fields.

### [Project 4](https://github.com/Rishikesh-Jadhav/CMSC848F-3D-Vision/tree/main/Project4): Point Cloud Classification and Segmentation

- **Learnings from Project 4**:

  1. **Classification Model Implementation:**
     - Developed an understanding of implementing a PointNet-based architecture for point cloud classification.
     - Learned to define model structures, handling input points from multiple classes (chairs, vases, lamps).
     - Explored model initialization, training, and testing procedures.
       <img src="reviews_and_presentations/outputs/a4_classific.png" width="60%">

  2. **Segmentation Model Implementation:**
     - Gained insights into implementing a PointNet-based architecture for point cloud segmentation.
     - Defined the model structure for segmentation tasks focusing on chair objects.
     - Executed model initialization, training, and segmentation result visualization.
       <img src="reviews_and_presentations/outputs/a4_seg.png" width="60%">

  3. **Experimentation and Robustness Analysis:**
     - Conducted two robustness experiments to evaluate the model's performance under different conditions.
     - Explored rotation of input point clouds by 15, 45, 90 degrees and varying the number of points per object by 10000, 5000, 1000.
     - Analyzed how these variations affected test accuracy and visually interpreted the results.

The completion of Project 4 provided a comprehensive hands-on experience with PointNet architectures, further strengthening skills in 3D vision tasks, neural network implementation, and robustness analysis in the context of point cloud data.

  
## Additional Resources
Huge thanks to Andrei Neagoie & Daniel Bourke for their ML Zero to mastery Bootcamp! 
- [Reference](https://zerotomastery.io/courses/machine-learning-and-data-science-bootcamp/)


