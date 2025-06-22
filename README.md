# Comparative Evaluation of Raven, metaFlye, and Read-Based Taxonomic Classification in Nanopore Metagenomic Pipelines

## Project Overview

This project evaluates the performance of assembly-based and read-based taxonomic classification workflows using long-read Oxford Nanopore Technologies (ONT) sequencing. Four microbial samples of varying complexity were sequenced on the ONT MinION and processed using two assemblers (Raven and metaFlye) and Kraken2 for taxonomic classification. The goal was to benchmark pipeline components and identify strengths and limitations in different analytical approaches.

📄 [Read the full paper (PDF)](https://github.com/leonavracar/metagen-reports/blob/main/final_paper.pdf)

## Dataset

* **Samples**: Oral swab, environmental room swab, single cultured microorganism, mock community (ZymoBIOMICS HMW DNA standard)
* **Sequencing Platform**: ONT MinION, R10.4.1 flow cell

## Tools and Methods

### Preprocessing

* **Adapter trimming & chimera removal**: Porechop
* **Quality filtering & read cropping**: NanoFilt
* **QC reports**: MinIONQC, FastQC, NanoPlot

### Assembly & Polishing

* **Assemblers**: Raven (default and custom parameters), metaFlye
* **Polishing**: Medaka
* **Assembly Quality Evaluation**: MetaQUAST

### Taxonomic Classification

* **Classifier**: Kraken2 (Standard PlusPF DB)
* **Visualization**: Krona via KrakenTools
* **Assembly graph visualization**: Bandage

## Objectives

1. Compare Raven vs. metaFlye for structural accuracy and completeness
2. Assess read-based vs. assembly-based classification for taxonomic resolution
3. Evaluate how preprocessing, assembly, and classification parameters affect final results

## Key Findings

* **Read-based classification** was more accurate for simple samples like the Zymo mock community.
* **Raven** yielded structurally cleaner assemblies; **metaFlye** produced more complete assemblies.
* **Polishing with Medaka** had minimal impact on structural changes but reduced base errors.
* Significant discrepancies were observed between taxonomic results from Kraken2 vs. MetaQUAST due to differing methodologies.
