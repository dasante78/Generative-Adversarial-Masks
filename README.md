# Generative Adversarial Masks: Safeguarding Images from AI Models with Stealthy Perturbations
6.8301 Project. By Daniel Prakah-Asante and Aileen Liao

## Project Overview
"Generative Adversarial Masks" (SPAM) is a research project focused on protecting images from being analyzed by AI models. The project develops a Stealth Perturbation Adaptive Model (SPAM) that applies image-specific perturbations to protect images from AI analysis while maintaining visual similarity.

## Key Features
- **Protection through Stealth Perturbations**: Masks generated using the SPAM model safeguard images from AI models by altering their representations.
- **Flexible Protection Levels**: The model allows for adjustable parameters to balance between image quality and protection based on the use case.
- **Evaluation on Multiple Datasets**: Tested on both Flickr30k and Dogs vs Cats datasets, demonstrating reduced AI classifier performance.

## Usage
To run the model:
1. Preprocess your image dataset to the required size (224x224 pixels).
2. Train the SPAM model using the included Python script (`train_SPAM.py`).
3. Adjust the epsilon parameter in the script to vary the strength of the perturbation mask.
4. Test the model's performance by running the evaluation script (`evaluate_SPAM.py`), which compares image quality and cosine similarity.

## Models
Several variations of the SPAM model were implemented:

- **Scaled Epsilons**: Adjusts the perturbation strength (ε) during training to control the ratio between image quality and protection.
- **Norm Models**: Minimize additional norms to improve image quality.
- **Secondary Loss Models**: Introduce gradient and magnitude losses to better preserve image structure while enhancing protection.
- **Alternative Loss Models**: Focus on collapsing the image's representation into uniform vectors.

## Evaluation
- **Image Quality**: The Structural Similarity Index Measure (SSIM) and Cosine Similarity metrics are used to evaluate the balance between protection and visual fidelity.
- **Model Robustness**: Testing on the Dogs vs Cats dataset demonstrated that SPAM-protected images reduced AI classifier accuracy from 99% to 48%.
  
## Results
- The **RGB-Gradient Model** showed the best performance in preserving image quality, achieving an average SSIM of 0.99.
- More aggressive protection models significantly degraded the performance of AI classifiers without sacrificing image quality.

## Conclusions
The SPAM model effectively protects images from AI analysis, balancing protection with image quality. The RGB-Gradient method proved most effective for applications where image quality is a priority. Future work will explore scaling the model to protect against more complex AI architectures and utilizing diffusion techniques for robust image protection.

## Future Work
- Expand the model to protect against advanced architectures like CLIP.
- Investigate the use of diffusion models for creating more robust protective masks.

## Acknowledgments
Special thanks to Professor Russell Tedrake, Ethan Yang, and the MIT staff for their guidance.

## License
This project is licensed under the MIT License.

## Citation
If you use or reference this project, please cite it as follows:

```bibtex
@misc{spam_protection_2024,
  title={Generative Adversarial Masks: Safeguarding Images from AI Models with Stealthy Perturbations},
  author={Prakah-Asante, Daniel and Liao, Aileen},
  year={2024},
  publisher={GitHub},
  journal={GitHub repository},
  howpublished={\url{https://github.com/username/generative-adversarial-masks}}
}
