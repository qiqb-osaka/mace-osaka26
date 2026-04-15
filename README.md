# MACE-Osaka models
This repository provides models and training scripts for the multi-domain universal machine learning interatomic potential (MLIP) series, MACE-Osaka.

The current lineup includes:
- **MACE-Osaka24**: a universal MLIP for crystalline and molecular domains, trained with a "Total Energy Alignment" dataset integration technique that combines first-principles calculations under various conditions.
- **MACE-Osaka26**: a universal MLIP trained on the MACE-Osaka24 dataset plus a newly constructed heavy-element dataset, **HE26**, extending coverage to **97 elements** across the periodic table.

MACE-Osaka26 integrates literature-based heavy-element data (including minor actinides) derived from experimental findings and theoretical calculations. By combining molecule, crystal, and heavy-element systems in one training framework, it is designed to deliver strong cross-domain generalization and support applications such as energy-resource development, such as actinide-based high-entropy ceramics design, in the nuclear field.

The models are based on the MACE framework. To use them, please install the [MACE code](https://github.com/ACEsuit/mace).

MACE version compatibility:
- **MACE-Osaka26**: compatible with MACE **v0.3.12 or later**
- **MACE-Osaka24**: compatible with MACE **v0.3.6 or later**

# **⚠️ Security Notice**
We have identified a malicious impersonation repository that appears to distribute suspicious release files under the name `mace-osaka26`.  
Please download release files **only from this official repository**.  
Do **not** download or run files from any other repository or unofficial source.

## Models

- First generation: [MACE-Osaka24](https://github.com/qiqb-osaka/mace-osaka24/releases/tag/v0.0.1)
- Second generation: [MACE-Osaka26](https://github.com/qiqb-osaka/mace-osaka26/releases/tag/v0.0.1) (97-element model with MPtrj+OFF23+HE26); training settings are available in [`mace_osaka26`](mace_osaka26)

If you use the models, in addition to citing the original MACE papers, please cite:

```bib
@misc{shiota2024taming,
    title={Taming Multi-Domain, -Fidelity Data: Towards Foundation Models for Atomistic Scale Simulations},
    author={Tomoya Shiota and Kenji Ishihara and Tuan Minh Do and Toshio Mori and Wataru Mizukami},
    year={2024},
    eprint={2412.13088},
    archivePrefix={arXiv},
    primaryClass={physics.chem-ph}
}

@misc{kuroda2026expandinguniversalmachinelearning,
      title={Expanding Universal Machine Learning Interatomic Potentials to 97 Elements Towards Nuclear Applications}, 
      author={Naoya Kuroda and Kenji Ishihara and Tomoya Shiota and Wataru Mizukami},
      year={2026},
      eprint={2603.03223},
      archivePrefix={arXiv},
      primaryClass={physics.chem-ph},
      url={https://arxiv.org/abs/2603.03223}, 
}
```

## Training scripts

We provide training scripts for both generations in this repository:

- MACE-Osaka24: [`mace_osaka24/mace-osaka24-small.sh`](mace_osaka24/mace-osaka24-small.sh), [`mace_osaka24/mace-osaka24-medium.sh`](mace_osaka24/mace-osaka24-medium.sh), [`mace_osaka24/mace-osaka24-large.sh`](mace_osaka24/mace-osaka24-large.sh)
- MACE-Osaka26: [`mace_osaka26/mace-osaka26-small.sh`](mace_osaka26/mace-osaka26-small.sh)

## Training data

MACE-Osaka24 is trained on an integrated inorganic-organic dataset composed of the inorganic MPtrj dataset and the organic SPICE, QMug, water clusters, and Tripeptides (OFF23) datasets. This integrated dataset is available at [figshare](https://figshare.com/articles/dataset/Inorganic_organic_domain_dataset/28023149).

MACE-Osaka26 is trained on a combined **97-element universal dataset** comprising:
- **MACE-Osaka24**: The complete training dataset described above (MPtrj and OFF23 integrated via TEA).
- **HE26**: A newly developed heavy-element dataset. It includes minor actinides and is based on a combination of experimental literature and theoretical calculations. HE26 is available on [figshare](https://doi.org/10.6084/m9.figshare.31429325)

With the HE26 extension, MACE-Osaka26 covers 97 elements and spans molecules, crystals, and heavy-element systems in a single universal MLIP.

If you use the publicly available component datasets listed above, please cite the following papers.

```bib
@article{deng2023chgnet,
      title={CHGNet: Pretrained universal neural network potential for charge-informed atomistic modeling},
      author={Bowen Deng and Peichen Zhong and KyuJung Jun and Janosh Riebesell and Kevin Han and Christopher J. Bartel and Gerbrand Ceder},
      year={2023},
      eprint={2302.14231},
      archivePrefix={arXiv},
      primaryClass={cond-mat.mtrl-sci}
}

@misc{kovacs2023maceoff23,
      title={MACE-OFF23: Transferable Machine Learning Force Fields for Organic Molecules}, 
      author={Dávid Péter Kovács and J. Harry Moore and Nicholas J. Browning and Ilyes Batatia and Joshua T. Horton and Venkat Kapil and William C. Witt and Ioan-Bogdan Magdău and Daniel J. Cole and Gábor Csányi},
      year={2023},
      eprint={2312.15211},
      archivePrefix={arXiv},
}

@article{eastman2023spice,
  title={Spice, a dataset of drug-like molecules and peptides for training machine learning potentials},
  author={Eastman, Peter and Behara, Pavan Kumar and Dotson, David L and Galvelis, Raimondas and Herr, John E and Horton, Josh T and Mao, Yuezhi and Chodera, John D and Pritchard, Benjamin P and Wang, Yuanqing and others},
  journal={Scientific Data},
  volume={10},
  number={1},
  pages={11},
  year={2023},
  publisher={Nature Publishing Group UK London}
}

@article{donchev2021quantum,
  title={Quantum chemical benchmark databases of gold-standard dimer interaction energies},
  author={Donchev, Alexander G and Taube, Andrew G and Decolvenaere, Elizabeth and Hargus, Cory and McGibbon, Robert T and Law, Ka-Hei and Gregersen, Brent A and Li, Je-Luen and Palmo, Kim and Siva, Karthik and others},
  journal={Scientific data},
  volume={8},
  number={1},
  pages={55},
  year={2021},
  publisher={Nature Publishing Group UK London}
}

@article{isert2022qmugs,
  title={QMugs, quantum mechanical properties of drug-like molecules},
  author={Isert, Clemens and Atz, Kenneth and Jim{\'e}nez-Luna, Jos{\'e} and Schneider, Gisbert},
  journal={Scientific Data},
  volume={9},
  number={1},
  pages={273},
  year={2022},
  publisher={Nature Publishing Group UK London}
}

@misc{shiota2024taming,
    title={Taming Multi-Domain, -Fidelity Data: Towards Foundation Models for Atomistic Scale Simulations},
    author={Tomoya Shiota and Kenji Ishihara and Tuan Minh Do and Toshio Mori and Wataru Mizukami},
    year={2024},
    eprint={2412.13088},
    archivePrefix={arXiv},
    primaryClass={physics.chem-ph}
}

@misc{kuroda2026expandinguniversalmachinelearning,
      title={Expanding Universal Machine Learning Interatomic Potentials to 97 Elements Towards Nuclear Applications}, 
      author={Naoya Kuroda and Kenji Ishihara and Tomoya Shiota and Wataru Mizukami},
      year={2026},
      eprint={2603.03223},
      archivePrefix={arXiv},
      primaryClass={physics.chem-ph},
      url={https://arxiv.org/abs/2603.03223}, 
}
```

## Example

In this example, the energy of a silicon crystal and acetic acid is calculated using a MACE-Osaka model (e.g., MACE-Osaka26 or MACE-Osaka24) and the Atomic Simulation Environment (ASE).

```python
from ase.build import bulk
from ase.build import molecule
from mace.calculators import MACECalculator

si = bulk('Si', 'diamond', a=5.43)
calculator = MACECalculator(model_path='/path-to-model/mace-osaka26-small.model', device='cpu')
si.calc = calculator 

energy_si = si.get_potential_energy()
print("Single-point energy of diamond Si:", energy_si)

acid = molecule('CH3COOH')
acid.calc = calculator 

energy_acid = acid.get_potential_energy()
print("Single-point energy of acetic acid:", energy_acid)
```

## Contributors
This project was developed by:

- Tomoya Shiota (@TShiotaSS) 
- Kuroda Naoya (@kurodanaoya)
- Kenji Ishihara (@kenji-ishihara-os)  
- Toshio Mori (@forest1040)
- Wataru Mizukami (@wmizukami)
