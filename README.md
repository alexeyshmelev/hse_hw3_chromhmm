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

| Состояние | Метка | Изображение | CpG островки рядом | Тип |
| :-----------: | :-----------: | :-----------: | :-----------: | :-----------: |
| 1 | Нет | ![image](https://user-images.githubusercontent.com/60858323/160300226-99fabac0-fcd3-4c5c-9184-0b8905ff6112.png) | Нет | Интрон |
| 2 | H3K27me3 | ![image](https://user-images.githubusercontent.com/60858323/160300226-99fabac0-fcd3-4c5c-9184-0b8905ff6112.png) | Нет | Интрон |
| 3 | H3K4me1 | ![image](https://user-images.githubusercontent.com/60858323/160300380-69faa10e-497d-4c3c-bd76-37fc2f126a0c.png) | Нет | Интрон |
| 4 | Нет | ![image](https://user-images.githubusercontent.com/60858323/160300509-c4a00d01-2b7e-41ce-ac51-5fa344d12b1d.png) | Нет | Интрон |
| 5 | H3K79me2 | ![image](https://user-images.githubusercontent.com/60858323/160300556-03bca4ee-9453-4555-a4c5-f64bb4cbbaa7.png) | Нет | Интрон |
| 6 | H3K79me2 | ![image](https://user-images.githubusercontent.com/60858323/160300556-03bca4ee-9453-4555-a4c5-f64bb4cbbaa7.png) | Нет | Интрон |
| 7 | H3K79me2 | ![image](https://user-images.githubusercontent.com/60858323/160300556-03bca4ee-9453-4555-a4c5-f64bb4cbbaa7.png) | Нет | Интрон |
| 8 | H3K4me3, H3K27ac | ![image](https://user-images.githubusercontent.com/60858323/160300144-ae56c311-5afb-4974-b7fa-e14c0b72165c.png) | Нет | Интрон |
| 9 | Нет | ![image](https://user-images.githubusercontent.com/60858323/160300462-92669740-bf86-42b3-92c7-4730bfecc237.png) | Нет | Интрон |
| 10 | Нет | ![image](https://user-images.githubusercontent.com/60858323/160300430-b0295be8-7c18-45ad-a6d7-508c717bdc45.png) | Нет | Экзон |


