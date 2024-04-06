# Chapter 3: Asset Creation for Film

## Section 3.1: What You Will Learn from This Chapter

### Topic Overview

* the process of creating digital assets for film
* the different types of assets creating during all 3 stages of film production
* technical concepts and key tools used in feature animation and VFX

### Production Pipeline Tasks

Carried out on set:
* data capture (LIDAR, lighting data, reference photography)

Carried out in the facility:
* processing live footage (plate prep, rotoscoping, camera tracking)
* modeling
* texture and shader creation
* layout
* rigging
* animation
* FX
* lighting
* compositing 

## Section 3.2: LIDAR and On-Set Survey Data

"**Total stations**" (instrument used in surveying for measuring angles and distances) and GPS are measuring tools that have been used in the film industry for several decades. **LIDAR scanners** were introduced in the late 1990s, allowing for more effective use of geospatial data in the production of VFX shots. 

### LIDAR

In LIDAR scanning, a laser measures the distance from a fixed location to points on surrounding rigid surfaces (e.g. buildings or props). The measurement data is stored as a **"point cloud"** (a series of disconnected points in 3D space) which can then be converted into digital 3D geometry.

The 3D model allows for the creation of:
* accurate digital backgrounds for VFX shots,
* set extensions,
* and to improve the accuracy of camera tracking.

### Reference Objects

It can be useful to include a reference object of known dimensions to demonstrate the scale of the set being scanned.

However, LIDAR scanners are survey-grade instruments, so this is sometimes automatic during setup. 

### Resolution

LIDAR technicians should always try to capture the entire set at high resolution where possible.

However, when time is limited, technicians need to prioritize the areas to be scanned in order of their probable importance in VFX work. With the _"selective resolution approach"_, areas of importance are captured at high resolution and less important areas at low resolution. 

Resolution of data can be reduced later, but the reverse is impossible.

### Decimation

Once scanning is complete, backup copies are made of the LIDAR scans. 

As LIDAR scanners are capable of recording billions of points that produce gigabytes of data, it is standard to deliver three versions:
* 10% decimated,
* 50% decimated,
* and the original high-res scan data for reference.

**Decimation** is achieved through algorithms that reduce the nubmer of triangles that make up the 3D surface generated from the point-cloud data while still preserving an accurate overall form.

### Data Collection & Organization

**Metadata** is collected during LIDAR scans using pen and paper or in digital data-entry sheets.

Raw reference material is sorted and transferred in a similar way:  the cameras used to collect reference material must be calibrated correctly with matching time stamps so that the data syncrhonizes properly with other reference sources. 

Given the sheer volume of data collected during a scan, file-naming conventions are important to avoid confusion.

### Data Mapping

Once the data is delivered to the VFX facility, it must be sorted so that it appears in the asset-management system in an easily navigable form. This is accomplished by **remapping** the data from the on-set database (date-ordered) to the facility's database, usually structured by shot or asset type. 

### Beyond LIDAR

There is additional data captured on set:
* chrome or gray ball data (images of reflective and matte spheres photographed on set) to be used as reference by artists to digitally recreate the same lighting conditions 
* HRDIs (High Dynamic Range Images)
* digital photography that will be used to create texture maps or as reference images 



