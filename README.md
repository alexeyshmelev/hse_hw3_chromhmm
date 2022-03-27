# Домашнее задание №3

## Исходный код

```
!curl -O https://raw.githubusercontent.com/deepjavalibrary/d2l-java/master/tools/fix-colab-gpu.sh && bash fix-colab-gpu.sh
!curl -O https://raw.githubusercontent.com/deepjavalibrary/d2l-java/master/tools/colab_build.sh && bash colab_build.sh
!java --list-modules | grep "jdk.jshell"
! wget http://compbio.mit.edu/ChromHMM/ChromHMM.zip
!unzip /content/ChromHMM.zip

! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneDnd41H2azAlnRep1.bam -O H2AFZ.bam
! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneDnd41H3k27acAlnRep1.bam -O H3K27ac.bam
! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneDnd41H3k27me3AlnRep1.bam -O H3K27me3.bam
! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneDnd41H3k36me3AlnRep1.bam -O H3K36me3.bam
! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneDnd41H3k04me1AlnRep1.bam -O H3K4me1.bam
! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneDnd41H3k04me2AlnRep1.bam -O H3K4me2.bam
! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneDnd41H3k04me3AlnRep1.bam -O H3K4me3.bam
! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneDnd41H3k79me2AlnRep1.bam -O H3K79me2.bam
! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneDnd41H3k09acAlnRep1.bam -O H3K9ac.bam
! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneDnd41H4k20me1AlnRep1.bam -O H4K20me1.bam

! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneDnd41ControlStdAlnRep1.bam -O control.bam

! java -mx5000M -jar /content/ChromHMM/ChromHMM.jar BinarizeBam -b 200  /content/ChromHMM/CHROMSIZES/hg19.txt /content/ cellmarkfiletable.txt   binarizedData
! java -mx5000M -jar /content/ChromHMM/ChromHMM.jar LearnModel /content/binarizedData output 10 hg19
! zip archive -r output
```

## Картинки из выдачи ChromHMM
![emissions_10](https://user-images.githubusercontent.com/60858323/160299069-eff6f4f6-76f4-43c5-8797-b9df381fd479.png)
![transitions_10](https://user-images.githubusercontent.com/60858323/160299114-35eb8b2c-ea52-4046-bb0e-da2cc715af72.png)
![Dnd41_10_overlap](https://user-images.githubusercontent.com/60858323/160299075-f38fb899-7a2d-455f-86ab-9d0a89fca05b.png)
![Dnd41_10_RefSeqTES_neighborhood](https://user-images.githubusercontent.com/60858323/160299079-ebc15d04-de1c-41f6-9347-2dda5951baf7.png)
![Dnd41_10_RefSeqTSS_neighborhood](https://user-images.githubusercontent.com/60858323/160299084-8639990d-3f17-43b7-8fca-6646dd14b111.png)

