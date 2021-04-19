# 3D_BRAIN_TUMOR_SEG
Deep-learning CNN model for fully automatic glioma segmentation in 3D volume of MRI data

<img src="https://www.med.upenn.edu/cbica/assets/user-content/images/BraTS/brats-tumor-subregions.jpg" alt="challenge def img">

<h3>Task 1: Segmentation of gliomas in pre-operative MRI scans.</h3><br>
<p>
   The sub-regions of tumor considered for evaluation are: 1) the "enhancing tumor" (ET), 2) the "tumor core" (TC), and 3) the "whole tumor" (WT) The provided segmentation labels have values of 1 for NCR & NET, 2 for ED, 4 for ET, and 0 for everything else.
</p><br>

<h2>Proposed solution</h2><br>

<p>U-NET 2D Architecture as CNN model for tumor segmentation task</p><br>
<img src="https://lmb.informatik.uni-freiburg.de/people/ronneber/u-net/u-net-architecture.png" width="60%" height="auto">
<p>U-net is convolutional network architecture for fast and precise segmentation of images. Up to now it has outperformed the prior best method (a sliding-window convolutional network) on the ISBI challenge for segmentation of neuronal structures in electron microscopic stacks.</p><br>


model = build_unet(input_layer, 'he_normal', 0.2)
model.compile(loss="categorical_crossentropy", optimizer=keras.optimizers.Adam(learning_rate=0.001), metrics = ['accuracy',tf.keras.metrics.MeanIoU(num_classes=4), dice_coef, precision, sensitivity, specificity, dice_coef_necrotic, dice_coef_edema ,dice_coef_enhancing] )

<h4>Training parameters:</h4><br>
<i>U-NET kernel initializers: 'he_normal' with 20% propability dropout. Model trained with loss='categorical_crossentropy', Adam optimizer with learning rate 0.001  </i><br>
<img src="https://www.kaggleusercontent.com/kf/59751358/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..GbV3FAcRhAuF8T_AJLXtdQ.c95gWOuHMephZuA9aPbM8DsWTSALlDkaJndWI98qx45J8uY5wmwaQCDKmwrc4qe3zRnDsnIV5sgKjumI9bRzJh-YZXvYO7qyjVUkXOvPnSateLgGkwpRu9tQo1uK8j1kTSDOoYKlijX8v6mNjBPH_xpGuKAndYo-68KGm_vbszbJbSDn_rlZ2XzfcoAFf1WgD6aihkf-JtkyYWCH5pQ0lb-gIFs2mHZLPDa8-h1VaKAFqJ5GVAt2MXhIBk7EARtikJY_2uOIIl62ZqCK0zUw9JL_kalQewMsKuqmGzprnS9nkI5UMUBkles4eSR6JxYrXfelHzCqg-2GA30_YA51QgE2CXxskqWDM9TnS23Y6EFq_youYsl7YOVIpzAcGR7iI2kbMSHg4CoAcicZcqF651M8EYJ4X-ingUt2yCzuwNEztBayJquZZNhvcOy6WWibbsWAjHbifEkQnzO6jHMQxV26YzAYtw39Wm2otTnz298inE4kudctixlD-WmQIuY2Sp0r_JjsBL9WrkzTe0P9uwIVjJTsiQa-H5C6xqOP3LQUKdAs9hLJq6TG8L4YBFee30Trca1LZEle7xRe-2x0gbScr6Y_cKeac7p3k-KJfe93gTKvyKNwwUBrOOTX0y55N4QJFLs0UXCfRRdVcRlioAZoiulNREhtx2p8R9PLY72-mrQaQ0TbfyJq7K0g1l5g.Z9Kdeg2yerBqyQcuaDWmeA/__results___files/__results___33_0.png" width="90%" height="auto">

<h4>Results</h4><br>
Mean IoU: <b>0.8442</b><br>
Mean dice coeficient: <b>0.6253</b><br>
Dice coef class: necrotic: <b>0.6001</b><br>
Dice coef class: edema: <b>0.7287</b><br>
Dice coef class: enhancing: <b>0.6366</b><br><br>

<hr><br>

<h3>Task 2: Survival days prediction</h3><br>
<p>

</p><br>

<h2>Proposed solution</h2><br>
