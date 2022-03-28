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

## Проанализированные гистоновые метки

| Гистоновая метка | Название файла |
| :-----------: | :-----------: |
| H2AFZ | H2AFZ.bam |
| H3K27ac | H3K27ac.bam |
| H3K27me3 | H3K27me3.bam |
| H3K36me3 | H3K36me3.bam |
| H3K4me1 | H3K4me1.bam |
| H3K4me2 | H3K4me2.bam |
| H3K4me3 | H3K4me3.bam |
| H3K79me2 | H3K79me2.bam |
| H3K9ac | H3K9ac.bam |
| H4K20me1 | H4K20me1.bam |

## Эпигенетические типы

| Состояние | Метка | Изображение | CpG островки рядом | Расположение относительно генов | Наличие рядом lamina associated domains | Тип |
| :-----------: | :-----------: | :-----------: | :-----------: | :-----------: | :-----------: | :-----------: |
| 1 | H2AFZ, H3K27ac, H3K27me3 | ![image](https://user-images.githubusercontent.com/60858323/160476333-15d3f34e-f030-489d-adb4-909a94586dc1.png) | Да | Везде | Нет | Transcribed |
| 2 | Нет | ![image](https://user-images.githubusercontent.com/60858323/160471592-1f1534b3-b703-4375-a7e0-ba1c185cbbdb.png) | На данном рисунке есть, но чаще всего нет | Вне гена | Нет | Repressed |
| 3 | Нет | ![image](https://user-images.githubusercontent.com/60858323/160473996-f2ba76a1-74a5-4fed-961e-bee67cdf72a3.png) | Да | Вне гена | Нет | Transcribed |
| 4 | H3K36me3 | ![image](https://user-images.githubusercontent.com/60858323/160472292-22f17d40-405a-40ea-8b98-c3bffa49c2fd.png) | Нет | Вне гена | Нет | Transcribed |
| 5 | H3K36me3 | ![image](https://user-images.githubusercontent.com/60858323/160477085-fb1d9030-aac9-40f3-bd20-be636b18275a.png) | Нет | Вне гена | Да | Transcribed |
| 6 | H3K36me3, H4K20me1 | ![image](https://user-images.githubusercontent.com/60858323/160474812-174ccdde-0a71-444a-8ee5-a564ea10f0b2.png) | Да | Вне гена | Нет | Transcribed |
| 7 | H3K79me2 | ![image](https://user-images.githubusercontent.com/60858323/160472827-5d7e900c-ce5c-4275-85ce-39b2816b0ab6.png) | Нет | Вне гена | Нет | Transcribed |
| 8 | H2AFZ, H3K27ac, H3K36me3, H3K4me1, H3K4me2, H3K4me3, H3K79me2, H3K9ac, H4K20me1 | ![image](https://user-images.githubusercontent.com/60858323/160471061-47a00050-cc8a-4a76-aac2-64d009eec115.png) | Да | Внутри гена | Нет | Transcribed |
| 9 | H2AFZ, H3K27ac, H3K4me1, H3K4me2, H3K4me3 | ![image](https://user-images.githubusercontent.com/60858323/160475374-ad220a0a-2633-493a-adc7-d988d244cbd6.png) | Да | В конце гена | Нет | Transcribed |
| 10 | H2AFZ, H3K27ac, H3K36me3, H3K4me1, H3K4me2, H3K4me3, H3K79me2, H3K9ac, H4K20me1 | ![image](https://user-images.githubusercontent.com/60858323/160469483-7a5ea789-45c4-4832-a083-99b78b62149b.png) | Да | В начале гена | Нет | Promoter |


