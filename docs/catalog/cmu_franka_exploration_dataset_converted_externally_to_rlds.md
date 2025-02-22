<div itemscope itemtype="http://schema.org/Dataset">
  <div itemscope itemprop="includedInDataCatalog" itemtype="http://schema.org/DataCatalog">
    <meta itemprop="name" content="TensorFlow Datasets" />
  </div>
  <meta itemprop="name" content="cmu_franka_exploration_dataset_converted_externally_to_rlds" />
  <meta itemprop="description" content="Franka exploring toy kitchens&#10;&#10;To use this dataset:&#10;&#10;```python&#10;import tensorflow_datasets as tfds&#10;&#10;ds = tfds.load(&#x27;cmu_franka_exploration_dataset_converted_externally_to_rlds&#x27;, split=&#x27;train&#x27;)&#10;for ex in ds.take(4):&#10;  print(ex)&#10;```&#10;&#10;See [the guide](https://www.tensorflow.org/datasets/overview) for more&#10;informations on [tensorflow_datasets](https://www.tensorflow.org/datasets).&#10;&#10;" />
  <meta itemprop="url" content="https://www.tensorflow.org/datasets/catalog/cmu_franka_exploration_dataset_converted_externally_to_rlds" />
  <meta itemprop="sameAs" content="https://human-world-model.github.io/" />
  <meta itemprop="citation" content="@inproceedings{mendonca2023structured,&#10;              title={Structured World Models from Human Videos},&#10;              author={Mendonca, Russell  and Bahl, Shikhar and Pathak, Deepak},&#10;              journal={RSS},&#10;              year={2023}&#10;            }" />
</div>

# `cmu_franka_exploration_dataset_converted_externally_to_rlds`


Note: This dataset was added recently and is only available in our
`tfds-nightly` package
<span class="material-icons" title="Available only in the tfds-nightly package">nights_stay</span>.

*   **Description**:

Franka exploring toy kitchens

*   **Homepage**:
    [https://human-world-model.github.io/](https://human-world-model.github.io/)

*   **Source code**:
    [`tfds.robotics.rtx.CmuFrankaExplorationDatasetConvertedExternallyToRlds`](https://github.com/tensorflow/datasets/tree/master/tensorflow_datasets/robotics/rtx/rtx.py)

*   **Versions**:

    *   **`0.1.0`** (default): Initial release.

*   **Download size**: `Unknown size`

*   **Dataset size**: `602.24 MiB`

*   **Auto-cached**
    ([documentation](https://www.tensorflow.org/datasets/performances#auto-caching)):
    No

*   **Splits**:

Split     | Examples
:-------- | -------:
`'train'` | 199

*   **Feature structure**:

```python
FeaturesDict({
    'episode_metadata': FeaturesDict({
        'file_path': Text(shape=(), dtype=string),
    }),
    'steps': Dataset({
        'action': Tensor(shape=(8,), dtype=float32),
        'discount': Scalar(shape=(), dtype=float32),
        'is_first': bool,
        'is_last': bool,
        'is_terminal': bool,
        'language_embedding': Tensor(shape=(512,), dtype=float32),
        'language_instruction': Text(shape=(), dtype=string),
        'observation': FeaturesDict({
            'highres_image': Image(shape=(480, 640, 3), dtype=uint8),
            'image': Image(shape=(64, 64, 3), dtype=uint8),
        }),
        'reward': Scalar(shape=(), dtype=float32),
        'structured_action': Tensor(shape=(8,), dtype=float32),
    }),
})
```

*   **Feature documentation**:

Feature                         | Class        | Shape         | Dtype   | Description
:------------------------------ | :----------- | :------------ | :------ | :----------
                                | FeaturesDict |               |         |
episode_metadata                | FeaturesDict |               |         |
episode_metadata/file_path      | Text         |               | string  | Path to the original data file.
steps                           | Dataset      |               |         |
steps/action                    | Tensor       | (8,)          | float32 | Robot action, consists of [end effector position3x, end effector orientation3x, gripper action1x, episode termination1x].
steps/discount                  | Scalar       |               | float32 | Discount if provided, default to 1.
steps/is_first                  | Tensor       |               | bool    |
steps/is_last                   | Tensor       |               | bool    |
steps/is_terminal               | Tensor       |               | bool    |
steps/language_embedding        | Tensor       | (512,)        | float32 | Kona language embedding. See https://tfhub.dev/google/universal-sentence-encoder-large/5
steps/language_instruction      | Text         |               | string  | Language Instruction.
steps/observation               | FeaturesDict |               |         |
steps/observation/highres_image | Image        | (480, 640, 3) | uint8   | High resolution main camera observation
steps/observation/image         | Image        | (64, 64, 3)   | uint8   | Main camera RGB observation.
steps/reward                    | Scalar       |               | float32 | Reward if provided, 1 on final step for demos.
steps/structured_action         | Tensor       | (8,)          | float32 | Structured action, consisting of hybrid affordance and end-effector control, described in Structured World Models from Human Videos.

*   **Supervised keys** (See
    [`as_supervised` doc](https://www.tensorflow.org/datasets/api_docs/python/tfds/load#args)):
    `None`

*   **Figure**
    ([tfds.show_examples](https://www.tensorflow.org/datasets/api_docs/python/tfds/visualization/show_examples)):
    Not supported.

*   **Examples**
    ([tfds.as_dataframe](https://www.tensorflow.org/datasets/api_docs/python/tfds/as_dataframe)):

<!-- mdformat off(HTML should not be auto-formatted) -->

{% framebox %}

<button id="displaydataframe">Display examples...</button>
<div id="dataframecontent" style="overflow-x:auto"></div>
<script>
const url = "https://storage.googleapis.com/tfds-data/visualization/dataframe/cmu_franka_exploration_dataset_converted_externally_to_rlds-0.1.0.html";
const dataButton = document.getElementById('displaydataframe');
dataButton.addEventListener('click', async () => {
  // Disable the button after clicking (dataframe loaded only once).
  dataButton.disabled = true;

  const contentPane = document.getElementById('dataframecontent');
  try {
    const response = await fetch(url);
    // Error response codes don't throw an error, so force an error to show
    // the error message.
    if (!response.ok) throw Error(response.statusText);

    const data = await response.text();
    contentPane.innerHTML = data;
  } catch (e) {
    contentPane.innerHTML =
        'Error loading examples. If the error persist, please open '
        + 'a new issue.';
  }
});
</script>

{% endframebox %}

<!-- mdformat on -->

*   **Citation**:

```
@inproceedings{mendonca2023structured,
              title={Structured World Models from Human Videos},
              author={Mendonca, Russell  and Bahl, Shikhar and Pathak, Deepak},
              journal={RSS},
              year={2023}
            }
```

