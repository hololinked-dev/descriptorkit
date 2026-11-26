# descriptorkit

[![CD Pipeline](https://github.com/hololinked-dev/descriptorkit/actions/workflows/cd-pipeline.yml/badge.svg)](https://github.com/hololinked-dev/descriptorkit/actions/workflows/cd-pipeline.yml)

Typed, validated and observable class attributes built on Python descriptors.

`descriptorkit` is derived from [HoloViz param](https://github.com/holoviz/param) and is maintained as the
parameter/descriptor layer of [hololinked](https://github.com/hololinked-dev/hololinked).

For the official param library, visit the upstream repository at [holoviz/param](https://github.com/holoviz/param).

## Install

```
pip install descriptorkit
```

Optional extras for numpy array and pandas parameters (`descriptorkit.extensions`):

```
pip install descriptorkit[numpy,pandas]
```

## Usage

```python
from descriptorkit import Parameterized
from descriptorkit.parameters import Integer, String


class Device(Parameterized):
    serial = String(default="unknown")
    channels = Integer(default=1, bounds=(1, 16))


d = Device()
d.channels = 8
d.channels = 32  # raises ValueError
```

## License

BSD-3-Clause, see [LICENSE](LICENSE). Original copyright belongs to the HoloViz team.
