# 3D_BRAIN_TUMOR_SEG
Deep-learning CNN model for fully automatic glioma segmentation in 3D volume of MRI data

<img src="https://www.med.upenn.edu/cbica/assets/user-content/images/BraTS/brats-tumor-subregions.jpg" alt="challenge def img">

<h1>Task 1: Segmentation of gliomas in pre-operative MRI scans.</h1><br>
<p>
   The sub-regions of tumor considered for evaluation are: 1) the "enhancing tumor" (ET), 2) the "tumor core" (TC), and 3) the "whole tumor" (WT) The provided segmentation labels have values of 1 for NCR & NET, 2 for ED, 4 for ET, and 0 for everything else.
</p><br>

<h2>Proposed solution</h2><br>

<p>U-NET 2D Architecture as CNN model for tumor segmentation task</p><br>
<img src="https://lmb.informatik.uni-freiburg.de/people/ronneber/u-net/u-net-architecture.png" width="60%" height="auto">
<p>U-net is convolutional network architecture for fast and precise segmentation of images. Up to now it has outperformed the prior best method (a sliding-window convolutional network) on the ISBI challenge for segmentation of neuronal structures in electron microscopic stacks.</p><br>

<h4>Training parameters:</h4><br>
<i>U-NET kernel initializers: 'he_normal' with 20% propability dropout. Model trained with loss='categorical_crossentropy', Adam optimizer with learning rate 0.001  </i><br>
<img src="https://www.kaggleusercontent.com/kf/59751358/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..GbV3FAcRhAuF8T_AJLXtdQ.c95gWOuHMephZuA9aPbM8DsWTSALlDkaJndWI98qx45J8uY5wmwaQCDKmwrc4qe3zRnDsnIV5sgKjumI9bRzJh-YZXvYO7qyjVUkXOvPnSateLgGkwpRu9tQo1uK8j1kTSDOoYKlijX8v6mNjBPH_xpGuKAndYo-68KGm_vbszbJbSDn_rlZ2XzfcoAFf1WgD6aihkf-JtkyYWCH5pQ0lb-gIFs2mHZLPDa8-h1VaKAFqJ5GVAt2MXhIBk7EARtikJY_2uOIIl62ZqCK0zUw9JL_kalQewMsKuqmGzprnS9nkI5UMUBkles4eSR6JxYrXfelHzCqg-2GA30_YA51QgE2CXxskqWDM9TnS23Y6EFq_youYsl7YOVIpzAcGR7iI2kbMSHg4CoAcicZcqF651M8EYJ4X-ingUt2yCzuwNEztBayJquZZNhvcOy6WWibbsWAjHbifEkQnzO6jHMQxV26YzAYtw39Wm2otTnz298inE4kudctixlD-WmQIuY2Sp0r_JjsBL9WrkzTe0P9uwIVjJTsiQa-H5C6xqOP3LQUKdAs9hLJq6TG8L4YBFee30Trca1LZEle7xRe-2x0gbScr6Y_cKeac7p3k-KJfe93gTKvyKNwwUBrOOTX0y55N4QJFLs0UXCfRRdVcRlioAZoiulNREhtx2p8R9PLY72-mrQaQ0TbfyJq7K0g1l5g.Z9Kdeg2yerBqyQcuaDWmeA/__results___files/__results___33_0.png" width="90%" height="auto">

<h4>Results</h4><br>
Mean IoU: <b>0.8442</b><br>
Mean dice coeficient: <b>0.6253</b><br>
Dice coef class: necrotic: <b>0.6001</b><br>
Dice coef class: edema: <b>0.7287</b><br>
Dice coef class: enhancing: <b>0.6366</b><br>

<h4>Predictions example:</h4><br>
<img src="https://www.kaggleusercontent.com/kf/59751358/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..YeuGMXGv1bmPVONhsAPAqQ.FdvguTRtvz11xqzO6Htcn9i7n6kCT1_Ih2PE-OjZghMEwrvcYEhE7Xc0IdBxvVwSFlG11l3d8Thyl4kUpxsW2N0BnZQterP2gQk8_kK4sUCpeD4W_D-GgT4bMtgXNWqARhYqkIpSQ_HUyeKtp_LqYWW3s7xxsYp-g___O_Ns0Qk3PdbWMD6MGmJXLvyjURWbx7sr6PxCV12TCJhrsWyqveSOE-p3JXubx_sbWNeYNymAKEveR2odxGTolW7XMcqzdgAVXPuwRWrjo-cstZBjSEgcfJDSw7hAkgL2edSEHMFPjDH6qdn_e7ZIcACKbuP5If9lLfOmUO9X6oth7LPDV4SEke-DrlIGsDtjRJINHji6KJ6MAIVfneLliW2yMPTFLmmSKobjdgHEITtzJyLkv8bIadshlDPl-pHbWT0saKPbZ2MS9rCDcg4low9m342MnvXoe2b2yPTD2qSo4O_fpzaJHa2NRL4wU-BZrgH3eABf8y40aSiIvQd5JPmTPDJ1B9FSu1RjrmTcDZ7HNWJsAS-Pu9iOCmnwZZOPftHSjXpOfAQxx_uscZUsr1KC9zf88Ry34Br_cPUMEQDddtLefJSIKDMsZE8uBjSxIBFnt_kuIJPZsqMHHnp2ZlVwkBg4mEA36MfTkgD25zHla8KzqcYmWDMoTSfUzDNwPjW_HLueMFwBCOs8bzCFYWmhSZ96._bHisTUPeWgm1MBv_nxfwA/__results___files/__results___36_8.png" width="80%" height="auto">
From left: original slice of a brain, ground truth, all classes predicted, CORE predicted, EDEMA predicted, ENHANCING predicted.

<hr><br>

<h1>Task 2: Survival days prediction</h1><br>
<p>
Our task is aimed at classifying patients into three survival groups obtained by unsupervised two-step clustering. These groups roughly correspond to the known survival groups in GBM (PMID: 22517216). The survival groups were characterized as long survivors (e.g., > 450 days), short survivors (e.g., < 300 days), and mid-survivors (e.g., between 300 and 450 days). For precise treatment planning, it is valuable to categorize a patient to either of these survival subgroups. This will enable clinicians to decide how aggressively a patient needs to be treated. 
</p><br>

<h2>Proposed solution</h2><br>
<p>We tried different solutions and compared results. For each model we also implemented GridSearch to find the best parameters for models. For training we are using 4 parameters which are ratios of volumes for each tumor category to the size of a brain and patient's age.</p><br>

<h4>Random forest classifier</h4><br>
<i>Hyperparameters: {'criterion': 'gini', 'n_estimators': 1}</i><br>
<b>Train Score: 0.42339181286549704<br>
Test Score: 0.4583333333333333</b><br>
<img src="https://www.kaggleusercontent.com/kf/60132695/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..CkVBNyTzZVQIiMSUQK1kpw.u8OjY7wLArshBMh_dJ60iggd-cyNFGC8ha-V_xKlVUILaWmDJml9RMC-93FIWKQJj__L8qN-Rgpfte7dt4Jny7laEm3FN4qYvJj5mQdsrYobhaqsjbFKaho5Qe-dose7sMkKc4qsdk1a09MY64bcDYd5DLZgqSp2zzIHyKAbRaRMyOuugPu5s5FYVX4JDaL4E_wEcgy7X8Fnnx9E-zQHSDvEcIHu1jOnqPfbQomOKdNAw_R1UXB2IzldJlaxsZ_HzFJbGgxBsiBvQjm07VaBk2XNAZDlAWGxIUqHrzjlYcLJgpqcp6Bf6Wyxz0y-UIjl0YKNJ_xN2D8EWtWZJdS_1ZnJIozqABQZrbg7VhjroGJH1_UdxuDEEnGo4UL2N5oJVj3eudFzu-45Ro7qyPCUNE_NDRoS2x3Debkqqv4J4MYXn27jukspsVPgXu5gEaIbO-KcE1PG-J1lwUAs5W1FxRxxkn_-_RayNnjSMtEZTRRmRpmHswmc0ZtJ0n5tasQVOGxXpmMkip2BKLVDtfEIdmJFlgyzwxz8m9RKOzCSVmIY-w8XwW7EiZWK5atwjiXUNjl-p6V4JWwkcoWNhCCA887iTkQ3dh_tTif6KJdXoEvIx2_sdHtPyEpG2b3tg2BKlSqhS7c6Rgca8wrrdbm_0574I2MDEtYcqaiYdWbSbSArXaDVwMIGplXpEsHXK2cQ.qmaz20XTVJZAqp6wDA_rIQ/__results___files/__results___32_0.png" width="40%" height="auto">

<h4>SVM classifier</h4><br>
<i>Hyperparameters: {'C': 10, 'degree': 3, 'gamma': 1, 'kernel': 'poly'}</i><br>
<b>Train Score: 0.5216374269005847<br>
Test Score: 0.5</b><br>
<img src="https://www.kaggleusercontent.com/kf/60132695/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..CkVBNyTzZVQIiMSUQK1kpw.u8OjY7wLArshBMh_dJ60iggd-cyNFGC8ha-V_xKlVUILaWmDJml9RMC-93FIWKQJj__L8qN-Rgpfte7dt4Jny7laEm3FN4qYvJj5mQdsrYobhaqsjbFKaho5Qe-dose7sMkKc4qsdk1a09MY64bcDYd5DLZgqSp2zzIHyKAbRaRMyOuugPu5s5FYVX4JDaL4E_wEcgy7X8Fnnx9E-zQHSDvEcIHu1jOnqPfbQomOKdNAw_R1UXB2IzldJlaxsZ_HzFJbGgxBsiBvQjm07VaBk2XNAZDlAWGxIUqHrzjlYcLJgpqcp6Bf6Wyxz0y-UIjl0YKNJ_xN2D8EWtWZJdS_1ZnJIozqABQZrbg7VhjroGJH1_UdxuDEEnGo4UL2N5oJVj3eudFzu-45Ro7qyPCUNE_NDRoS2x3Debkqqv4J4MYXn27jukspsVPgXu5gEaIbO-KcE1PG-J1lwUAs5W1FxRxxkn_-_RayNnjSMtEZTRRmRpmHswmc0ZtJ0n5tasQVOGxXpmMkip2BKLVDtfEIdmJFlgyzwxz8m9RKOzCSVmIY-w8XwW7EiZWK5atwjiXUNjl-p6V4JWwkcoWNhCCA887iTkQ3dh_tTif6KJdXoEvIx2_sdHtPyEpG2b3tg2BKlSqhS7c6Rgca8wrrdbm_0574I2MDEtYcqaiYdWbSbSArXaDVwMIGplXpEsHXK2cQ.qmaz20XTVJZAqp6wDA_rIQ/__results___files/__results___38_0.png" width="40%" height="auto">

<h4>K Neighbors Classifier</h4><br>
<i>Hyperparameters: {'n_neighbors': 38, 'p': 2, 'weights': 'distance'}</i><br>
<b>Train Score: 0.49941520467836253<br>
Test Score: 0.5416666666666666</b><br>
<img src="https://www.kaggleusercontent.com/kf/60132695/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..CkVBNyTzZVQIiMSUQK1kpw.u8OjY7wLArshBMh_dJ60iggd-cyNFGC8ha-V_xKlVUILaWmDJml9RMC-93FIWKQJj__L8qN-Rgpfte7dt4Jny7laEm3FN4qYvJj5mQdsrYobhaqsjbFKaho5Qe-dose7sMkKc4qsdk1a09MY64bcDYd5DLZgqSp2zzIHyKAbRaRMyOuugPu5s5FYVX4JDaL4E_wEcgy7X8Fnnx9E-zQHSDvEcIHu1jOnqPfbQomOKdNAw_R1UXB2IzldJlaxsZ_HzFJbGgxBsiBvQjm07VaBk2XNAZDlAWGxIUqHrzjlYcLJgpqcp6Bf6Wyxz0y-UIjl0YKNJ_xN2D8EWtWZJdS_1ZnJIozqABQZrbg7VhjroGJH1_UdxuDEEnGo4UL2N5oJVj3eudFzu-45Ro7qyPCUNE_NDRoS2x3Debkqqv4J4MYXn27jukspsVPgXu5gEaIbO-KcE1PG-J1lwUAs5W1FxRxxkn_-_RayNnjSMtEZTRRmRpmHswmc0ZtJ0n5tasQVOGxXpmMkip2BKLVDtfEIdmJFlgyzwxz8m9RKOzCSVmIY-w8XwW7EiZWK5atwjiXUNjl-p6V4JWwkcoWNhCCA887iTkQ3dh_tTif6KJdXoEvIx2_sdHtPyEpG2b3tg2BKlSqhS7c6Rgca8wrrdbm_0574I2MDEtYcqaiYdWbSbSArXaDVwMIGplXpEsHXK2cQ.qmaz20XTVJZAqp6wDA_rIQ/__results___files/__results___44_0.png" width="40%" height="auto">
