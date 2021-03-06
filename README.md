# language-evaluation (Experimental)
Collection of evaluation code for natural language generation.

## Metrics
- coco-caption (BLEU1-4, METEOR, ROUGE, CIDEr, SPICE)

## Requirements
- Java 1.8.0+
- Python 3.6+

## Installation and Usuage

Install Java 1.8.0+. Then run:
```bash
pip install git+https://github.com/bckim92/language-evaluation.git
python -c "import language_evaluation; language_evaluation.download('coco')"
```

Python API:
```python
import language_evaluation
from pprint import PrettyPrinter
pprint = PrettyPrinter().pprint

evaluator = language_evaluation.Evaluator()
predicts = ['i am a boy', 'she is a girl']
answers = ['am i a boy ?', 'is she a girl ?']
results = evaluator.run_evaluation(predicts, answers, method="coco")
pprint(results)
# {'Bleu_1': 0.9999999998823529,
#  'Bleu_2': 0.8944271908911816,
#  'Bleu_3': 0.7174075809792958,
#  'Bleu_4': 0.563321871690505,
#  'CIDEr': 6.308531746031747,
#  'METEOR': 0.5128174590570939,
#  'ROUGE_L': 0.8285714285714285,
#  'SPICE': 0.6111111111111112}
```

## Notes
- TODOs
  - Support more metrics (e.g. rouge-1,2,L and embedding-based)
  - Support command-line interface
  - Add tests & CI

## Related Projects
- [tylin/coco-caption](https://github.com/tylin/coco-caption)
- [bckim92/coco-caption-py3](https://github.com/bckim92/coco-caption-py3)
- [Maluuba/nlg-eval](https://github.com/Maluuba/nlg-eval)

## License
See [LICENSE.md](LICENSE.md).
