# RRIS40 Test Dataset

## Specifications
- 10 subjects
- total of ~0.1 million frames with raw 3D marker positions.
- 3D data from a marker-based motion capture system (Qualisys)
    - 200 fps
    - positions of 40+6 markers in TSV format (Labels and definitions of all markers can be found [here](https://koonyook.github.io/rris40/markers))
- Data from RGB Video Cameras
    - 8 synchronized global shutter cameras
    - 1920 x 1200 resolution
    - 50 fps
    - h.264 encoding
    - intrinsic calibration parameters
    - extrinsic calibration parameters (in the Qualisys coordinate reference frame)
- Frame-level hardware synchronization is used between Qualisys' Miqus sync unit and all the RGB cameras. 
- The formulation to interpolate 3D marker positions at the center of frame exposure time and projection to the video frame is provided in the data viewer source code.  
    
## Organization
- Data from each subject is stored in one zip file such as SN123g.zip or FT321g.zip. Each zip file contains one or more record folders inside.
- Each record folder has the following structure
    - **YYYY-MM-DD-HH-mm-ss/** is called a record folder which contains data from only one continuous record.
        - **qualisys.tsv** contains data from the marker-based motion capture system
        - **metadata.pkl** contains metadata on the video record
        - **systemCalibration.pkl** contains calibration parameters of all the video cameras
        - **keepMarker{camera_id}.h264** contains encoded video content.
        - **keepMarker{camera_id}.seek** Do not remove this file.
        - **frameInfo{camera_id}.dat** Do not remove this file. 
    
## Download
You can download them [here](https://entuedu-my.sharepoint.com/:f:/g/personal/guanming001_e_ntu_edu_sg/Ei3fcq8jXB1DoueH6PK0V98BcIF1uPC_qA5xAkO_VQHJsA).
Password can be found in the paper.

**WARNING**: All the files are ~21GB in total.

## Want to visualize the dataset quickly?

The runnable Python source code is available [here](https://github.com/koonyook/rris40DataViewer). It simply playback a video with an overlay of 2D marker projections. This code allows you to understand our file structure to continue your work.

# Cite Us
If you gain something from our dataset, please cite our publication.
```
bibtex will be here soon.
```

# Additional Paper Supplementary

## Qualitative Results 
- Videos of qualitative results on assistive outfits are accessible through this [link](https://entuedu-my.sharepoint.com/:f:/g/personal/guanming001_e_ntu_edu_sg/EiI-kItTnDBFuzJGuHU0134BKuuj2CJIjEhVlsri73G4ig?e=mL67k1).

# Contact Us
- Prayook Jatesiktat. prayook001@e.ntu.edu.sg
- Guan Ming Lim. guanming001@e.ntu.edu.sg

We are from Nanyang Technological University.
