# Gene-expression-data-analysis

Potential interactions between estrogen receptor (ER) and RAD21 in MCF7 breast cancer cells were examined. Breast cancer is the most commonly diagnosed cancer in the female population and 70% of breast cancers express ER. ER agonism contributes to the cell cycle progression of ER-positive breast cancer cells by regulating transcription of target genes. RAD21 is a subunit of cohesin and is involved in holding sister chromatids together, DNA repair, and gene regulation. RAD21 controls gene expression by bringing distal DNA elements into proximity. MCF7 is a breast cancer cell line that has been broadly used for cancer research, and genome wide studies in MCF7 cells have shown that cohesin co-binds to DNA with ER at numerous sites. Determining which genes are differentially expressed between estrogen treatment vs. control and estrogen treatment with RAD21 knockdown vs. control indicates potential genes that are estrogen responsive whose expression is influenced by RAD21. 

<!-- wp:image {"id":9211,"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://gtbinf.files.wordpress.com/2019/11/workflow2.png?w=784" alt="" class="wp-image-9211"/><figcaption> Figure 1. Workflow of gene expression analysis of GSE114260 (RNA-Seq) and GSE59908 (microarray) datasets. </figcaption></figure>
<!-- /wp:image -->

Datasets GSE114260 and GSE59908 were analyzed. Dataset GSE114260, “Effect of estrogen (E2) treatment on the C4-12 relative to the MCF7 cells,” is composed of RNA-seq data from an Illumina HiSeq 2000 using cDNA made from polyA RNA. We assessed differential gene expression between vehicle (n =3; samples GSM3138572, GSM3138573, GSM3138574) and estrogen treated (48 hr; n=3; samples GSM3138575, GSM3138576, GSM3138577) MCF7 breast cancer cells. First, the SRA sample files were retreived from the Gene Expresison Omnius (GEO) and converted to fastq files and only reads with a quality score greater than 33 were used. Transcript abundance was quantified with Kallisto (2) using a reference transcriptome obtained from NCBI. In Sleuth, a likelihood ratio test and Wald test were performed and only genes that had a q ≤ 0.05 for both tests were kept. False discovery rate (FDR) values were calculated using the method of Benjamini and Hochberg. Prior to p-value calculation, genes were filtered to only include transcripts with a minimum of  five transcripts in at least 47% of samples. Differentially expressed genes were identified if fold change was ≥ 2, and q ≤ 0.05.

The list of differentially expressed genes was compared to data published by Petrossian et al. (2018). Petrossian et al. found a total of 2,595 differentially expressed genes. We found 2,857 using the same q value and fold change cutoffs. The full list of differentially expressed genes was not published. However, a list of 29 differentially expressed genes was published, and the top ten genes in terms of fold change were all found within the list (genes: B3GNT6, C5AR2, GREB1, GRIK3, HR, HSPB8, IGFBP4, PGLYRP2, PGR, and TUBA3E). The list of differentially expressed genes represents genes which are likely estrogen responsive. Hierarchical clustering, heat mapping, and principal component analysis (PCA) were performed using ExAtlas (8). Samples from the same treatment all clustered together in the heatmap indicating that the treatment had an effect on gene expression and the PCA shows that 38% of variation is explained by principal component one and 57% is explained by components one and two. 


<!-- wp:image {"id":9005,"sizeSlug":"medium"} -->
<figure class="wp-block-image size-medium"><img src="https://gtbinf.files.wordpress.com/2019/11/rna-seq-pca.png?w=289" alt="" class="wp-image-9005"/><figcaption> Figure 3. PCA of differentially expressed genes and samples from GSE114260 was performed using ExAtlas with the following thresholds: fold change ≥2 and FDR ≤ 0.05.  </figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":9005,"sizeSlug":"medium"} -->
<figure class="wp-block-image size-medium"><img src="https://gtbinf.files.wordpress.com/2019/11/rna-seq-pca.png?w=289" alt="" class="wp-image-9005"/><figcaption> Figure 3. PCA of differentially expressed genes and samples from GSE114260 was performed using ExAtlas with the following thresholds: fold change ≥2 and FDR ≤ 0.05.  </figcaption></figure>
<!-- /wp:image -->

Dataset GSE59908, “Expression data from MCF7 cells depleted of the cohesin subunit RAD21 and treated with estrogen or vehicle,” is composed of microarray data from a PrimeView Affymetrix Human Gene Expression Array using total RNA. We assessed differential gene expression between control siRNA and vehicle (n=3; samples GSM1453440, GSM1453441, GSM1453442) and RAD21 siRNA knockdown and estrogen treatment (6hr; n=3; GSM1453443, GSM1453444, GSM1453445). We used an ExAtlas pairwise comparison to generate a list of differentially expressed genes. Significance was determined by z score (z = |m1 - m2| / sqrt[ErrVar*((1/n1)+(1/n2))] where ErrVar is the error variance estimated from the error model of ANOVA. From the z score ExAtlas estimates p-values and calculates a FDR correction using the method of Bejamini-Hochnberg which is used to determine significance. FDR ≤ 0.05 and fold change  ≥  2 were used as the criteria for statistical significance. 

Measuring gene expression in the MCF7 cell line during estrogen receptor stimulation with RAD21 downregulation indicates genes that are estrogen responsive with a reduction of RAD21. Antony et al. (2015) did not publish a list of genes that were differentially expressed between the samples that were compared. The following genes were pulled from the text of Antony et al. and were found within the list: TMPRSS3, SOX4, CXCL12, TFF2, THBS1, CXCL12, IRS2, DKK1. Hierarchical clustering, heat mapping, and PCA were performed using ExAtlas. Samples from the same treatment all clustered together in the heatmap indicating that the treatment had an effect on gene expression and the PCA indicates that 87% of variation is explained by principal component 1 and 93% is explained by components one and two.  

<!-- wp:image {"id":9007,"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://gtbinf.files.wordpress.com/2019/11/microarray-heatmap.png?w=1024" alt="" class="wp-image-9007"/><figcaption> Figure 4. Hierarchical clustering of differentially expressed genes and samples in GSE59908 was performed using ExAtlas with the following thresholds: fold change ≥ 2 and FDR ≤ 0.05.  </figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":9009,"sizeSlug":"medium"} -->
<figure class="wp-block-image size-medium"><img src="https://gtbinf.files.wordpress.com/2019/11/microarray-pca.png?w=300" alt="" class="wp-image-9009"/><figcaption> Figure 5. PCA of samples in GSE59908 was performed using ExAtlas with the following thresholds: fold change ≥2 and FDR ≤ 0.05.&nbsp;<br><br> </figcaption></figure>
<!-- /wp:image -->

There are 71 unique genes that are differentially expressed in both datasets. These genes are candidate genes for estrogen responsive genes whose expression is modulated by RAD21. Local pathway analysis was performed with DAVID (4,5) using KEGG pathways. Three pathways were identified as being over represented in our overlapping differentially expressed gene list with the axon guidance pathway having the lowest p-value and four of the overlapping differentially expressed genes: CXCL12, RND1, EFNA1, and SEMA4C. 

<!-- wp:image {"id":9292,"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://gtbinf.files.wordpress.com/2019/11/overlapping-genes.png?w=312" alt="" class="wp-image-9292"/><figcaption>Figure 6. Overlapping differentially expressed genes between GSE114260 and GSE59908</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":9166,"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://gtbinf.files.wordpress.com/2019/11/kegg-pathways.png?w=1004" alt="" class="wp-image-9166"/><figcaption>Figure 7. Local pathway analysis of genes which were differentially expressed in both datasets using DAVID.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":9171,"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://gtbinf.files.wordpress.com/2019/11/axon-guidance-pathway.png?w=901" alt="" class="wp-image-9171"/><figcaption>Figure 8.  Axon guidance pathway from DAVID with overlapping differentially expressed genes indicated with red stars. </figcaption></figure>
<!-- /wp:image -->

Global pathway analysis was performed with Reactome (3) using the differentially expressed genes found for both microarray and RNA-seq datasets. Pathways in the signal transduction, vesicle transport, neuronal, and gene expression systems were the most over represented. 

<!-- wp:image {"id":9195,"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://gtbinf.files.wordpress.com/2019/11/reactomepathways.png?w=843" alt="" class="wp-image-9195"/><figcaption>Figure 9. Global pathway analysis of overlapping differentially expressed genes using Reactome.</figcaption></figure>
<!-- /wp:image -->

Reactome also identified the axon guidance pathway as being over represented with eight elements of the pathway in our list of genes: TUBA3D, TUBA3E, SDC2, RET, SIAH2, CXCl12, EFNA1, and RND1.

<!-- wp:image {"id":9199,"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://gtbinf.files.wordpress.com/2019/11/axon-guidance-pathway-reactome-1.png?w=1024" alt="" class="wp-image-9199"/><figcaption>Figure 10. Axon guidance pathway from Reactome indicating portions significantly over represented in our overlapping differentially expressed genes list in yellow.</figcaption></figure>
<!-- /wp:image -->

To identify genes which were most likely to be estrogen responsive and influenced by RAD21 both data sets were qualtile normalized and Z scores for overlapping differentially expressed genes were calculated and the genes by difference in Z score between the two datasets were ranked. It should be noted that a direct comparison cannot be made between the two datasets as RNA-Seq and microarray have different signal biases. However, an attempt was made to normalize the datasets as much as possible to allow a rational ranking of candiate genes. Three of the top 30 candidate genes (FGFBP2, ITPRIPL2, and KCNK6) overlapped with a list of 67 candidate genes from Antony et al. yielding a represendation factor of 26.3 and a p-value of 0.000199. Of the top 30 candidate genes only the axon guidance pathway was over represented using DAVID. All three of the genes that overlapped with Antony et al.'s candidate genes have been identified as target genes for RAD21 in ChIP-seq datasets from the ENCODE Transcription Factor Targets dataset (6). 

In conclusion, 71 genes were identified and three pathways which are potentially coregulated by estrogen and RAD21 in MCF7 breast cancer cells. Coregulation of each candidate gene should be verified with qPCR by comparing estrogen treated cells and estrogen treated cells with RAD21 downregulation. Understanding how estrogen and RAD21 interact to influence gene expression in cancer cells may inform drug discovery and design, diagnosis, and treatment of estrogen responsive cancers. 

