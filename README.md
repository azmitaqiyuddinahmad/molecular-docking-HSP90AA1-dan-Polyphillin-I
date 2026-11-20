Molecular Docking HSP90AA1 dan Polyphillin I

Dalam uji _in silico_, _Molecular Docking_ HSP90AA1 berperan dalam memprediksi pose konformasi dan afinitas ikatan antara ligan kandidat obat dengan protein targetnya. Saya menganalisis interaksi antara protein target HSP90AA1 (_Heat Shock Protein 90 Alpha Family Class A Member 1_, PDB ID: 3O0I) dengan senyawa alami Polyphyllin I (PPI) sebagai ligan uji, dan ligan bawaan kristal (P54) sebagai kontrol validasi.

| Kategori | Keterangan |
| --- | --- |
| Protein Target | HSP90AA1 |
| PDB ID | 3O0I |
| Resolusi | 1.47 Å |
| Ligan | Polyphillin I (CID: 11018329) |
| SMILES | C\[C@@H\]1CC\[C@@\]2(\[C@H\](\[C@H\]3\[C@@H\](O2)C\[C@@H\]4\[C@@\]3(CC\[C@H\]5\[C@H\]4CC=C6\[C@@\]5(CC\[C@@H\](C6)O\[C@H\]7\[C@@H\](\[C@H\](\[C@@H\](\[C@H\](O7)CO)O\[C@H\]8\[C@@H\](\[C@H\](\[C@@H\](O8)CO)O)O)O)O\[C@H\]9\[C@@H\](\[C@@H\](\[C@H\](\[C@@H\](O9)C)O)O)O)C)C)C)OC1 |

Langkah awal yang dilakukan adalah studi literatur terkait mekanisme inhibisi HSP90AA1, dilanjutkan dengan pencarian struktur kristal protein target melalui _database_ RCSB PDB (PDB ID: 3O0I dengan resolusi 1.47 Å) serta pengambilan kode Isomeric SMILES senyawa Polyphyllin I melalui PubChem (CID: 11018329). Tantangan utama pada tahap preparasi ligan adalah ukuran molekul Polyphyllin I yang besar sehingga pada _database_ hanya tersedia struktur 2D-nya. Untuk mengonversinya menjadi struktur 3D yang siap di-_docking_, layanan web NIH CACTUS dengan kode Isomeric SMILES dari PubChem digunakan. Selanjutnya, preparasi protein dilakukan di UCSF ChimeraX dengan menghapus molekul air dan ligan bawaan (P54) agar ruang kantung aktif tetap steril dari tumpang tindih sterik, diikuti penambahan hidrogen polar serta muatan parsial standar makromolekul (muatan Kollman / AMBER). Sementara itu, preparasi ligan dilakukan di ChimeraX dan penambahan muatan Gasteiger dengan AutoDockTools.

Simulasi _molecular docking_ dijalankan menggunakan AutoDock Vina. Penentuan koordinat pusat ruang pencarian (_Search Space_ / _Grid Box_) didasarkan pada hasil prediksi kantung pengikatan terbaik (_Rank_ 1) dari platform PrankWeb (**Gambar 1**), yaitu pada koordinat (-3.3930, -10.0745, -26.0613) dengan _Pocket Score_ sebesar 55.56 dan probabilitas 0.983 yang mencakup 42 residu asam amino utama.

![C:\\Users\\User\\OneDrive\\Pictures\\Screenshots\\Screenshot 2026-11-15 160045.png](images/image-001.png)

Gambar 1. Pencarian koordinat _center box_ dan kantung aktif terbaik pada reseptor HSP90AA1 (PDB ID: 3O0I) melalui PrankWeb

Simulasi ini menghasilkan 20 model konformasi untuk masing-masing ligan. Untuk mengevaluasi kekuatan pengikatan Polyphyllin I, redocking dilakukan terhadap ligan kontrol bawaan P54 pada _grid box_ yang sama sebagai pembanding.

![](images/image-002.png)Tabel 1. Hasil afinitas _molecular docking_ Polyphyllin I (PPI) – HSP90AA1

Tabel 2. Hasil afinitas molecular docking kontrol P54 – HSP90AA1

![](images/image-003.png)

Berdasarkan Tabel 1, konformasi terbaik (Model 1) dari Polyphyllin I menghasilkan nilai _Calculated Affinity_ sebesar -9.181 kcal/mol, sedangkan pada Tabel 2, ligan kontrol bawaan P54 menghasilkan nilai afinitas terbaik sebesar -8.750 kcal/mol. Nilai energi bebas ikatan Polyphyllin I yang jauh lebih negatif dibandingkan ligan kontrol bawaannya mengindikasikan bahwa Polyphyllin I memiliki afinitas pengikatan yang lebih kuat dan mampu membentuk kompleks yang lebih stabil di dalam situs aktif HSP90AA

![](images/ppi2D.png)

Gambar 2. Visualisasi 3D pose konformasi terbaik Polyphyllin I (Model 1) di dalam kantung aktif protein HSP90AA1 menggunakan UCSF ChimeraX.

![ppi2d](ppi yeay2.png/*ppi yeay2.png*)

Gambar 3. Diagram interaksi 2D antara ligan Polyphyllin I dengan residu asam amino pada situs aktif HSP90AA1 menggunakan BIOVIA Discovery Studio Visualizer.

Berdasarkan **Gambar 2**, molekul Polyphyllin I terlihat masuk dan terakomodasi dengan baik di dalam celah kantung aktif HSP90AA1. Hasil analisis interaksi 2D pada Gambar 3 memperkuat temuan tersebut dengan menunjukkan pembentukan dua ikatan hidrogen konvensional (_Conventional Hydrogen Bond_) yang kuat antara gugus hidroksil pada rantai gula Polyphyllin I dengan residu asam amino kunci ASP A:93 dan GLY A:135 (residu penting dalam pengikatan ATP serta inhibitor spesifik HSP90AA1). Selain itu, bagian kerangka cincin steroid Polyphyllin I distabilkan oleh interaksi hidrofobik Pi-Alkyl dengan residu TYR A:61, interaksi _Carbon Hydrogen Bond_ dengan ASN A:51, serta gaya Van der Waals dari residu di sekitar kantung aktif seperti VAL A:150, PHE A:138, LEU A:107, MET A:98, dan ALA A:55.

Simulasi molecular docking ini membuktikan bahwa Polyphyllin I berpotensi sebagai kandidat inhibitor alami HSP90AA1. Hal tersebut ditunjukkan oleh nilai afinitas pengikatannya (-9.181 kcal/mol) yang lebih unggul dibandingkan kontrol bawaan P54 (-8.750 kcal/mol) melalui pembentukan ikatan hidrogen kunci dengan residu ASP A:93 dan GLY A:135. Berdasarkan praktikum _in silico ini_, dapat dipahami bahwa tahapan fundamental dalam menghasilkan prediksi interaksi molekuler yang reliabel meliputi konversi struktur 3D ligan yang akurat, pembersihan heteroatom protein, penambahan muatan yang sesuai, serta penentuan koordinat _grid box_ yang presisi.

Daftar pustaka

Bugnon, M., Röhrig, U. F., Goullieux, M., Perez, M. A. S., Daina, A., Michielin, O., & Zoete, V. (2024). SwissDock 2024: major enhancements for small-molecule docking with Attracting Cavities and AutoDock Vina. Nucleic Acids Research, 52(W1), W316–W320. https://doi.org/10.1093/nar/gkae331

Eberhardt, J., Santos-Martins, D., Tillack, A. F., & Forli, S. (2021). AutoDock Vina 1.2.0: New docking methods, expanded force field, and Python bindings. Journal of Chemical Information and Modeling, 61(8), 3891–3898. [https://doi.org/10.1021/acs.jcim.1c00203](https://doi.org/10.1021/acs.jcim.1c00203)

Meng, E. C., Goddard, T. D., Pettersen, E. F., Couch, G. S., Pearson, Z. J., Morris, J. H., & Ferrin, T. E. (2023). UCSF ChimeraX: Tools for structure building and analysis. _Protein Science_, 32(11), e4792. [https://doi.org/10.1002/pro.4792](https://doi.org/10.1002/pro.4792)

National Cancer Institute. (n.d.). Online SMILES Translator and Structure File Generator \[Computer software\]. CADD Group Chemoinformatics Tools and User Services, National Institutes of Health. https://cactus.nci.nih.gov/translate/
