# Kaggle - Freesound Audio Tagging 2019

[www.kaggle.com/competitions/freesound-audio-tagging-2019/overview](https://www.kaggle.com/competitions/freesound-audio-tagging-2019/overview)

Competencia de Kaggle organizada como la segunda tarea del desafío DCASE 2019: “Audio tagging with noisy labels and minimal supervision”, en la que se debe construir un sistema de aprendizaje automático que realice **clasificación multi‑etiqueta de clips de audio**. En esta competencia se brinda un conjunto de datos con etiquetas “ruidosas” y cantidades limitadas de datos manualmente etiquetados, utilizando un vocabulario de 80 categorías del **AudioSet Ontology**.

Para que el *pipeline* del documento `FreesoundAudioTagging.ipynb` funcione correctamente, hay que crear los **TFRecord** con los *datasets* de la competencia. Para esto, se utilizan funciones auxiliares en el archivo `record.ipynb`, simplemente ejecutando un código similar al siguiente y adjuntando las direcciones correctas del *dataset*:

```python
save_to_tfrecord(
    train_curated_df,
    base_dir / 'train_curated',
    label_to_index,
    len(all_labels),
    base_dir / 'train_curated.tfrecord'
)

save_to_tfrecord_test(
    test_df,
    base_dir / 'test_resampled/test_resampled',
    base_dir / 'test_resampled.tfrecord'
)
```
