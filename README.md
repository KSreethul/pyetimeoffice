# pyetimeoffice — ETimeOffice Python Integration

[![Python Version](https://img.shields.io/badge/python-3.10+-blue)](https://www.python.org/)
[![License](https://img.shields.io/badge/license-LGPL--3.0-yellow)](https://www.gnu.org/licenses/lgpl-3.0.html)
[![PyPI version](https://img.shields.io/pypi/v/pyetimeoffice.svg)](https://pypi.org/project/pyetimeoffice/)

**pyetimeoffice** is a Python integration library for ETimeOffice biometric attendance systems and APIs.

It helps developers integrate ETimeOffice attendance devices and punch data into Django HRMS platforms, ERP systems, employee management software, and custom Python applications.

The library provides a simple interface for downloading attendance punch records, handling API responses, normalizing dates and times, and working with attendance data programmatically using HTTP Basic authentication.

---

## Keywords

ETimeOffice API, ETimeOffice integration, biometric attendance integration, attendance API, Django attendance integration, HRMS attendance API, Python attendance library, biometric API integration.

---

## Features

- Fetch punch data with timestamps (`DownloadPunchData`)
- Fetch punch data with MCID (`DownloadPunchDataMCID`)
- Fetch combined in/out punch data (`DownloadInOutPunchData`)
- Normalize API date, time, and datetime fields automatically
- Validate date ranges before API requests
- HTTP Basic authentication support
- Easy integration with Django HRMS and ERP systems
- Lightweight Python API client for ETimeOffice systems

---

## Installation

Install from PyPI:

```bash
pip install pyetimeoffice
```

Or install directly from GitHub:

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
- requests>=2.0

---

## Quick Start

```python
from pyetimeoffice import ETimeOfficeAPI

api = ETimeOfficeAPI(
    username="your_username",
    password="your_password",
    base_url="https://api.etimeoffice.com/api/",
)

# Download punch data
data = api.download_punch_data(
    from_date="25/03/2025_00:00",
    to_date="25/03/2025_12:22",
    emp_code="ALL",
)

# Download punch data with MCID
mcid_data = api.download_punch_data_mcid(
    from_date="25/03/2025_00:00",
    to_date="25/03/2025_12:22",
)

# Download in/out punch data
in_out = api.download_in_out_punch_data(
    from_date="25/03/2025",
    to_date="25/03/2025",
    emp_code="ALL",
)

print(data)
```

---

## Example Use Cases

- Django HRMS attendance synchronization
- Employee biometric attendance tracking
- Attendance analytics dashboards
- ERP attendance integrations
- Attendance automation workflows
- Payroll attendance processing
- Biometric attendance monitoring systems

---

## Project Structure

```text
pyetimeoffice/
├── __init__.py
├── biometric.py
```

See `pyetimeoffice/biometric.py` for ETimeOffice API integration implementation details.

---

## Building for Distribution

Install build tools:

```bash
pip install build
```

Build package:

```bash
python -m build
```

Artifacts will be generated inside the `dist/` directory.

---

## Publishing to PyPI

Upload package using Twine:

```bash
pip install twine
twine upload dist/*
```

---

## Contributing

Contributions are welcome.

1. Fork the repository
2. Create a feature branch

```bash
git checkout -b feature-name
```

3. Commit your changes
4. Push to your branch
5. Open a Pull Request

---

## License

This project is licensed under **LGPL-3.0-only** (GNU Lesser General Public License v3.0 only).

See the [`LICENSE`](./LICENSE) file for more details.

---

## Links

- Homepage: https://github.com/KSreethul/pyetimeoffice
- PyPI: https://pypi.org/project/pyetimeoffice/
- Bug Tracker: https://github.com/KSreethul/pyetimeoffice/issues
- ETimeOffice API: https://api.etimeoffice.com/

---

## Topics

Python, ETimeOffice, attendance API, biometric attendance, Django HRMS integration, attendance synchronization, ERP integration, employee attendance systems.