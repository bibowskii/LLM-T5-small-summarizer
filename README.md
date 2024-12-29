# README: XSUM Training Process

## Overview
This document outlines the process of training a T5-small model for summarization using the XSUM dataset in three distinct rounds. Each round builds upon the output model from the previous round. Due to runtime restrictions, the training was conducted across multiple Google Colab accounts, requiring adjustments to model paths between rounds.

## Dataset
- **Type**: XSUM
- **Purpose**: Summarization task
- **Characteristics**: High-quality and concise summaries for articles

## Training Process
### Round 1
1. **Input Model**: Pre-trained T5 model
2. **Dataset**: 'iohadrubin/mini_xsum'
3. **Output Model Path**: `round1_output_model` (save this model for subsequent rounds)
4. **Colab Account**: Account 1
5. **Note**: Ensure that the output model is downloaded and backed up for use in the next round.

### Round 2
1. **Input Model**: `round1_output_model`
2. **Dataset**: 'woshityj/xsum_dataset'
3. **Output Model Path**: `round2_output_model` (save this model for subsequent rounds)
4. **Colab Account**: Account 2
5. **Adjustments**: Update the path to the `round1_output_model` to match the new Colab environment before starting training.

### Round 3
1. **Input Model**: `round2_output_model`
2. **Dataset**: 'Kamaljp/xsum_3000'
3. **Output Model Path**: `round3_output_model` (final trained model)
4. **Colab Account**: Account 3
5. **Adjustments**: Update the path to the `round2_output_model` to match the new Colab environment before starting training.

## Validation and testing
-Once the final model (round3_output_model) is trained, it can be validated and tested on new article data for summarization. Ensure the model performs well on unseen examples, and adjust parameters as necessary.

## Model demo
-After training the final model, you can use it to summarize new articles.

## Key Considerations
- **Model Path Adjustments**: As training spanned multiple Colab accounts, the output model paths from each round must be explicitly updated in the subsequent account.
  - Example: Download `round1_output_model` from Account 1 and upload it to Account 2 before initiating Round 2.
- **Runtime Restrictions**: Ensure sufficient runtime and GPU availability for each training session.
- **Consistency**: Verify that the dataset remains consistent across rounds to ensure uniformity in training.

## Final Output
- The final model (`round3_output_model`) is trained through three successive rounds of fine-tuning using the XSUM dataset. It can now be used for high-quality summarization tasks.

## Notes
- Always verify that the correct model is loaded at the start of each round.
- Maintain proper naming conventions and version control for models to avoid confusion.
- For further fine-tuning or deployment, ensure the final model is accessible in a centralized location.

### Contact
For issues or questions related to this training process, please reach out to the respective Colab account holders.

