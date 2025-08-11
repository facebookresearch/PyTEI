# PyTEI
- PyTEI: A User-friendly, Efficient, and Flexible Hardware Error Injection Framework for PyTorch

## Highlights
- User-friendly:
    - Completely PyTorch-based. No other dependency required ever. (It is recommended use packages such as `timeit` and `tqdm` for auxiliary purposes and running the examples / demos.)
    - No need to compile, build or even use custom environments.
- Efficient:
    - Uses `torch.view()` for bit flip operations, which significantly (about 100X) accelerates the error injection effort compared with other error injection tools.
- Flexible:
    - Works for any PyTorch model as long as they are implemented as `torch.nn.Module` with named parameters.
    - Implements two mitigation methods for emulation: activation filtering and selective bit protection in `depytei.py` and allows user customization.
    - Allows user to define their customized error model such as random value error beyond the provided bit flip error.

## Usage Examples / Demos
 - Install the dependencies in `requirements.yml`:
 ```bash
    conda env create --name PyTEI --file=requirements.yml
 ```

- Examples: see notebooks in `./examples`
    - (Quick Start) Error injection to Vision Transformers: `./examples/ViT.ipynb`
    - Evaluating and Enhancing Robustness of Deep Recommendation Systems Against Silent Hardware Errors: `./examples/DRS/`

## To-do:
- [X] Allow users to determine the device of generating and injecting errors.
- [X] Automatic error map size allocation by iterating through model.
- [X] Support for save and load of error maps with option to save as sparse tensor.
- [X] Implement for stuck-at-fault error (with customized error map).
- [X] Implement error mitigation methods of activation limiting and selective bit protection (SBP).
- [X] Allow users to specify individual parameters for error mitigation.
- [ ] Support for random value error.
- [ ] Support for 64-bit double precision.
- [ ] Support error injection during training.
- [ ] Support for quantized data types.

## Contributing

We welcome contributions to PyTEI! If you'd like to add new tests, fix existing issues, or improve the benchmark in any way, please fork this repository and submit a pull request.

## License

PyTEI is released under the MIT License.

## Citing
If you find this repo useful in your research, please consider citing us:
```
@inproceedings{ma2025understanding,
  title={Understanding Recommendation System Robustness Against Silent Data Corruption: An Empirical Study},
  author={Ma, Dongning and Jiao, Xun and Lin, Fred, and Moore, Daniel, and Sankar, Sriram},
  booktitle={2025 IEEE International Symposium on Software Reliability Engineering (ISSRE)},
  year={2025},
  organization={IEEE}
}
```
