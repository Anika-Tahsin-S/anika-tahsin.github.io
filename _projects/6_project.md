---
layout: page
title: Multiple Sequence Alignment (MSA) with Genetic Algorithm + Qwen2.5
description: GA-based MSA with PyTorch GPU fitness and local LLM JSON analysis
img: assets/img/projects/msa/cover.jpg
importance: 1
category: solo
related_publications: true
---

- Implemented a lightweight genetic-algorithm–based multiple sequence alignment (MSA) on Kaggle’s *Sequence Alignment (Bioinformatics) Dataset*.
- Integrated affine gap penalties (PAM250/BLOSUM62), tournament selection, residue-count–preserving crossover, and improving mutations. 
- Accelerated fitness evaluation with PyTorch on GPU (sum-of-pairs with affine gaps), plus elitism and immigration per generation.  
- Exported best alignments in **CLUSTAL (.aln)** and **FASTA (.fasta)** formats.  
- Computed per-column conservation (entropy), gap density, and pairwise % identity; visualized with heatmaps and dendrograms.  
- Enhanced interpretability with a local LLM (Qwen2.5-1.5B via llama-cpp, no API keys), producing validated JSON reports of conserved blocks, gap clusters, and closest/divergent sequence pairs.  

**Repo:** [Github](https://github.com/Anika-Tahsin-S/Multiple-Sequence-Alignment-with-GeneticAlgorithm-Qwen2.5)  
**Dataset:** [Kaggle Dataset](https://www.kaggle.com/datasets/samira1992/sequence-alignment-bioinformatics-dataset/data)  
**Model:** [Qwen2.5-1.5B-Instruct (GGUF)](https://huggingface.co/Qwen/Qwen2.5-1.5B-Instruct)

<div class="row">
  <!-- Left column: Entropy + Gap Density stacked -->
  <div class="col-sm mt-3 mt-md-0">
    <div class="mb-3">
      {% include figure.liquid loading="eager" path="assets/img/projects/msa/entropy.png" title="Entropy per column" class="img-fluid rounded z-depth-1" %}
    </div>
    <div>
      {% include figure.liquid loading="eager" path="assets/img/projects/msa/gap_density.png" title="Gap density plot" class="img-fluid rounded z-depth-1" %}
    </div>
  </div>

  <!-- Right column: Pairwise Identity Heatmap -->
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/projects/msa/pid_heatmap.png" title="Pairwise identity heatmap" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

<div class="caption">
  Left (top): Column-wise conservation (entropy). Left (bottom): Gap density across alignment. Right: Pairwise % identity heatmap of aligned sequences.
</div>



**Highlights**
- Frameworks: PyTorch, Biopython, matplotlib, llama-cpp-python  
- GA features: Affine gaps, tournament selection, residue-preserving crossover, improving mutations, elitism, immigration  
- Outputs: CLUSTAL/FASTA alignments, entropy & gap plots, identity heatmap, UPGMA dendrogram, JSON report  
- LLM integration: Qwen2.5-1.5B (local, no API) for automated alignment summaries
