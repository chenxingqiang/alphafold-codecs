# AlphaFold2 Algorithm Index

This document provides a comprehensive mapping between the 32 algorithms from the AlphaFold2 supplementary materials and their implementations in the source code.

## Quick Reference Table

| Algorithm | Name | Source File | Class/Function | Lines |
|-----------|------|-------------|----------------|-------|
| 1 | MSABlockDeletion | `model/tf/data_transforms.py` | Data augmentation | 214 |
| 2 | Inference | `model/modules.py` | `AlphaFold`, `AlphaFoldIteration` | 123-391 |
| 3 | InputEmbedder | `model/modules.py` | `EmbeddingsAndEvoformer` | 1694-1760 |
| 4 | relpos | `model/modules.py` | `EmbeddingsAndEvoformer` | 1744-1758 |
| 5 | one_hot | `model/modules.py` | `EmbeddingsAndEvoformer` | 1745 |
| 6 | EvoformerStack | `model/modules.py` | `EvoformerIteration` | 1553-1671 |
| 7 | MSARowAttentionWithPairBias | `model/modules.py` | `MSARowAttentionWithPairBias` | 712-776 |
| 8 | MSAColumnAttention | `model/modules.py` | `MSAColumnAttention` | 779-831 |
| 9 | MSATransition | `model/modules.py` | `Transition` | 476-529 |
| 10 | OuterProductMean | `model/modules.py` | `OuterProductMean` | 1414-1498 |
| 11 | TriangleMultiplicationOutgoing | `model/modules.py` | `TriangleMultiplication` | 1250-1337 |
| 12 | TriangleMultiplicationIncoming | `model/modules.py` | `TriangleMultiplication` | 1250-1337 |
| 13 | TriangleAttentionStartingNode | `model/modules.py` | `TriangleAttention` | 892-951 |
| 14 | TriangleAttentionEndingNode | `model/modules.py` | `TriangleAttention` | 892-951 |
| 15 | PairTransition | `model/modules.py` | `Transition` | 476-529 |
| 16 | TemplatePairStack | `model/modules.py` | `TemplatePairStack` | 393-473 |
| 17 | TemplatePointwiseAttention | `model/modules.py` | `TemplateEmbedding` | 2014-2092 |
| 18 | ExtraMsaStack | `model/modules.py` | `EmbeddingsAndEvoformer` | 1781-1812 |
| 19 | MSAColumnGlobalAttention | `model/modules.py` | `MSAColumnGlobalAttention`, `GlobalAttention` | 622-709, 834-889 |
| 20 | StructureModule | `model/folding.py` | `StructureModule`, `FoldIteration` | 281-559 |
| 21 | rigidFrom3Points | `model/r3.py` | `rigids_from_3_points` | 78-110 |
| 22 | InvariantPointAttention | `model/folding.py` | `InvariantPointAttention` | 37-279 |
| 23 | BackboneUpdate | `model/folding.py` | `FoldIteration` | 362-374 |
| 24 | computeAllAtomCoordinates | `model/all_atom.py` | `torsion_angles_to_frames`, `frames_and_literature_positions_to_atom14_pos` | 452-600 |
| 25 | makeRotX | `model/all_atom.py` | Inside `torsion_angles_to_frames` | 453 |
| 26 | renameSymmetricGroundTruthAtoms | `model/folding.py` | `compute_renamed_ground_truth` | 561-615 |
| 27 | torsionAngleLoss | `model/folding.py` | `supervised_chi_loss` | 854-911 |
| 28 | computeFAPE | `model/all_atom.py` | `frame_aligned_point_error` | 1025-1100 |
| 29 | predictPerResidueLDDT | `model/modules.py` | `PredictedLDDTHead` | 999-1100 |
| 30 | RecyclingInference | `model/modules.py` | `AlphaFold` | 344-390 |
| 31 | RecyclingTraining | `model/modules.py` | `AlphaFold` | 344-390 |
| 32 | RecyclingEmbedder | `model/modules.py` | `EmbeddingsAndEvoformer` | 1716-1741 |

## Source Files Overview

### `model/modules.py`
Contains the main neural network modules:
- Input embedding (Algorithm 3-5)
- Evoformer blocks (Algorithm 6-15)
- Template processing (Algorithm 16-17)
- Extra MSA processing (Algorithm 18-19)
- Recycling (Algorithm 30-32)
- pLDDT prediction (Algorithm 29)

### `model/folding.py`
Contains the Structure Module:
- Structure prediction (Algorithm 20)
- IPA attention (Algorithm 22)
- Backbone updates (Algorithm 23)
- Loss functions (Algorithm 26-27)

### `model/all_atom.py`
Contains atomic coordinate handling:
- Coordinate computation (Algorithm 24-25)
- FAPE loss (Algorithm 28)

### `model/r3.py`
Contains 3D geometry utilities:
- Rigid body operations (Algorithm 21)

### `model/tf/data_transforms.py`
Contains data preprocessing:
- MSA block deletion (Algorithm 1)

## Notebook Status

| Notebook | Status | Has Test Code |
|----------|--------|---------------|
| algorithm-1-MSABlockDeletion.ipynb | Empty | No |
| algorithm-2-Inference.ipynb | Empty | No |
| algorithm-3-InputEmbedder.ipynb | ✅ Complete | Yes |
| algorithm-4-relpos.ipynb | Empty | No |
| algorithm-5-one_hot.ipynb | Empty | No |
| algorithm-6-EvoformerStack.ipynb | ✅ Complete | Yes |
| algorithm-7-MSARowAttentionWithPairBias.ipynb | ✅ Complete | Yes |
| algorithm-8-MSAColumnAttention.ipynb | ✅ Complete | Yes |
| algorithm-9-MSATransition.ipynb | ✅ Complete | Yes |
| algorithm-10-OuterProductMean.ipynb | ✅ Complete | Yes |
| algorithm-11-TriangleMultiplicationOutgoing.ipynb | ✅ Complete | Yes |
| algorithm-12-TriangleMultiplicationIncoming.ipynb | ✅ Complete | Yes |
| algorithm-13-TriangleAttentionStartingNode.ipynb | ✅ Complete | Yes |
| algorithm-14-TriangleAttentionEndingNode.ipynb | Empty (covered by Alg 13) | No |
| algorithm-15-PairTransition.ipynb | Empty | No |
| algorithm-16-TemplatePairStack.ipynb | Empty | No |
| algorithm-17-TemplatePointwiseAttention.ipynb | Empty | No |
| algorithm-18-ExtraMsaStack.ipynb | Empty | No |
| algorithm-19-MSAColumnGlobalAttention.ipynb | Empty | No |
| algorithm-20-StructureModule.ipynb | ✅ Complete | Yes |
| algorithm-21-rigidFrom3Points.ipynb | ✅ Complete | Yes |
| algorithm-22-InvariantPointAttention.ipynb | ✅ Complete | Yes |
| algorithm-23-BackboneUpdate.ipynb | Empty | No |
| algorithm-24-computeAllAtomCoordinates.ipynb | Empty | No |
| algorithm-25-makeRotX.ipynb | Empty | No |
| algorithm-26-renameSymmetricGroundTruthAtoms.ipynb | Empty | No |
| algorithm-27-torsionAngleLoss.ipynb | Empty | No |
| algorithm-28-computeFAPE.ipynb | ✅ Complete | Yes |
| algorithm-29-predictPerResidueLDDT.ipynb | ✅ Complete | Yes |
| algorithm-30-RecyclingInference.ipynb | Empty | No |
| algorithm-31-RecyclingTraining.ipynb | Empty | No |
| algorithm-32-RecyclingEmbedder.ipynb | Empty | No |

## Key Architecture Components

### 1. Evoformer (Algorithms 6-15)
The central iterative refinement module:
```
Input: MSA representation (m), Pair representation (z)

For each block:
  m = m + RowAttention(m, z)      # Alg 7
  m = m + ColumnAttention(m)      # Alg 8
  m = m + Transition(m)           # Alg 9
  z = z + OuterProductMean(m)     # Alg 10
  z = z + TriMulOut(z)            # Alg 11
  z = z + TriMulIn(z)             # Alg 12
  z = z + TriAttnStart(z)         # Alg 13
  z = z + TriAttnEnd(z)           # Alg 14
  z = z + Transition(z)           # Alg 15

Output: Refined m, z
```

### 2. Structure Module (Algorithms 20-24)
Converts representations to 3D coordinates:
```
Input: Single representation (s), Pair representation (z)

Initialize: T = identity rigid transforms

For each iteration:
  s = s + IPA(s, z, T)            # Alg 22
  s = s + Transition(s)
  T = T ∘ BackboneUpdate(s)       # Alg 23
  
sidechains = PredictTorsions(s)   # Alg 24
atoms = ComputeAtomCoords(T, sidechains)

Output: Atom coordinates
```

### 3. Loss Functions (Algorithms 26-28)
```
FAPE = FrameAlignedPointError(predicted, target)  # Alg 28
chi_loss = TorsionAngleLoss(angles)               # Alg 27
```

## Running the Notebooks

Each completed notebook can be run standalone with NumPy. Example:

```bash
cd AF2-NoteBooks
jupyter notebook algorithm-6-EvoformerStack.ipynb
```

The notebooks include:
1. Algorithm pseudocode from the paper
2. Source code references
3. NumPy implementation for testing
4. Example inputs and outputs
5. Verification tests
