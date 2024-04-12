# python-chzzk

An unofficial Python library for CHZZK.

**Caution**: APIs are currently experimental.

## Requirements

- Python 3.8+

## Installation

```python
pip install git+https://github.com/billy0402/python-chzzk.git
# or
pipenv install git+https://github.com/billy0402/python-chzzk.git
```

## Uninstallation

```python
pip uninstall python-chzzk
# or
pipenv uninstall python-chzzk
```

## Usage

```python
import asyncio

from chzzk import Chzzk, Credential


async def main():
    credential = Credential(
        auth="Your NID_AUT",
        session="Your NID_SES",
    )
    chzzk = Chzzk(credential)

    print(await chzzk.me())
    print(await chzzk.channel("bdc57cc4217173f0e89f63fba2f1c6e5"))
    print(await chzzk.video(1794))
    print(await chzzk.search.channels("풍월량"))
    print(await chzzk.search.videos("자낳대"))
    print(await chzzk.search.lives("타르코프"))
    print(await chzzk.live.status(channel_id="22bd842599735ae19e454983280f611e"))
    print(await chzzk.live.detail(channel_id="22bd842599735ae19e454983280f611e"))


if __name__ == "__main__":
    asyncio.run(main())
```

## Common Error

```shell
pydantic_core._pydantic_core.ValidationError: 2 validation errors for Video
```

CHZZK is still in beta, so it will update its API models frequently.

This kind of error is caused by CHZZK updating API models, so it can't pass the pydantic model validations.

Please create an issue to let me know.

## Bugs and suggestions

If you have found a bug or have a request for additional functionality, please use the issue tracker on GitHub.

https://github.com/billy0402/python-chzzk/issues

## Acknowledgement

- Thanks to [kimcore/chzzk](https://github.com/kimcore/chzzk) for sharing API urls and explaining how it works.
- Thanks to [jonghwanhyeon/python-chzzk](https://github.com/jonghwanhyeon/python-chzzk), it's the original version of python-chzzk.
