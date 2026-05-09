# pyetimeoffice

[![Python Version](https://img.shields.io/badge/python-3.10+-blue)](https://www.python.org/)
[![License](https://img.shields.io/badge/license-LGPL--3.0-yellow)](https://www.gnu.org/licenses/lgpl-3.0.html)

**pyetimeoffice** is a Python library that provides an easy interface to the [ETimeOffice](https://api.etimeoffice.com/) API: download punch records, normalize dates and times from API responses, and work with attendance data programmatically via HTTP Basic authentication.

---

## Features

- Fetch punch data with timestamps (`DownloadPunchData`).
- Fetch punch data with MCID (`DownloadPunchDataMCID`).
- Fetch combined in/out punch data (`DownloadInOutPunchData`).
- Validates date ranges and converts response fields to `datetime`, `date`, and `time` where applicable.
- Works with ETimeOffice using HTTP Basic authentication.

---

## Installation

Install via pip (when published):

```
pip install pyetimeoffice
```

Or clone the repository and install locally:

```bash
git clone https://github.com/KSreethul/pyetimeoffice.git
cd pyetimeoffice
pip install .
```

Editable install during development:

```bash
pip install -e .
```

---

## Requirements

- Python 3.10+
- `requests>=2.0`

---

## Usage

```python
from pyetimeoffice import ETimeOfficeAPI

api = ETimeOfficeAPI(
    username="...",
    password="...",
    base_url="https://api.etimeoffice.com/api/",
)

data = api.download_punch_data(
    from_date="25/03/2025_00:00",
    to_date="25/03/2025_12:22",
    emp_code="ALL",
)

mcid_data = api.download_punch_data_mcid(
    from_date="25/03/2025_00:00",
    to_date="25/03/2025_12:22",
)

in_out = api.download_in_out_punch_data(
    from_date="25/03/2025",
    to_date="25/03/2025",
    emp_code="ALL",
)
```

See `pyetimeoffice/biometric.py` for implementation details.

---

## Building for distribution

```bash
pip install build
python -m build
```

Artifacts are written to `dist/`.

---

## Contributing

Contributions are welcome.

1. Fork the repository.
2. Create a new branch: `git checkout -b feature-name`.
3. Make your changes and commit.
4. Push to your branch and open a Pull Request.

---

## License

This project is licensed under **LGPL-3.0-only** (GNU Lesser General Public License v3.0 only). See the [`LICENSE`](./LICENSE) file in this repository or the canonical [LGPL v3 text](https://www.gnu.org/licenses/lgpl-3.0.html).

---

## Links

- **Homepage:** [https://github.com/KSreethul/pyetimeoffice](https://github.com/KSreethul/pyetimeoffice)
- **Bug Tracker:** [https://github.com/KSreethul/pyetimeoffice/issues](https://github.com/KSreethul/pyetimeoffice/issues)
