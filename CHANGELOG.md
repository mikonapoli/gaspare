# Release notes

<!-- do not remove -->

## 0.3.2


### Bugs Squashed

- Properly compute Flash 2.5 costs ([#10](https://github.com/mikonapoli/gaspare/issues/10))


## 0.3.1

### New Features

- Add Gemini 2.5 Flash and Thinking budget ([#9](https://github.com/mikonapoli/gaspare/issues/9))



## 0.3.0
### Breaking Changes

- Make Gaspare's `content` function compatible with Claudette's ([#8](https://github.com/mikonapoli/gaspare/issues/8))
  - `content` currently returns a dictionary, but Claudette expects it to return just the text content of the response. This requires some breaking change (although minimal)


### Bugs Squashed

- Long prompts cause OS errors ([#7](https://github.com/mikonapoli/gaspare/issues/7))
  - ```python
from gaspare import *

m = models[4] # 2.0 flash experimental
cli = Client(model=m)

prompt = '''\
Given a user description of an image, you will create a beautiful rendition of it, making sure to add in details that might not be present in the user's description but can be inferred. Only output the image, nothing else.

<desc>
Make a beautiful swan by a lake.
</desc>
'''
res = cli(prompt)
```

Running the above results in this error:

```
OSError: [Errno 63] File name too long: "Given a user description of an image, you will create a beautiful rendition of it, making sure to add in details that might not be present in the user's description but can be inferred. Only output the image, nothing else.\n\n<desc>\nMake a beautiful swan by a lake.\n</desc>\n"
```


## 0.2.2


### Bugs Squashed

- Long prompts cause OS errors ([#7](https://github.com/mikonapoli/gaspare/issues/7))
  - ```python
from gaspare import *

m = models[4] # 2.0 flash experimental
cli = Client(model=m)

prompt = '''\
Given a user description of an image, you will create a beautiful rendition of it, making sure to add in details that might not be present in the user's description but can be inferred. Only output the image, nothing else.

<desc>
Make a beautiful swan by a lake.
</desc>
'''
res = cli(prompt)
```

Running the above results in this error:

```
OSError: [Errno 63] File name too long: "Given a user description of an image, you will create a beautiful rendition of it, making sure to add in details that might not be present in the user's description but can be inferred. Only output the image, nothing else.\n\n<desc>\nMake a beautiful swan by a lake.\n</desc>\n"
```


## 0.2.1

- Fixes the release adding all the files


## 0.2.0

### New Features

- Add async Client and Chat ([#3](https://github.com/mikonapoli/gaspare/issues/3))



## 0.1.5


### Bugs Squashed

- Local videos not working properly ([#6](https://github.com/mikonapoli/gaspare/issues/6))
  - Providing a video from a local path raises the following:

```
ClientError: 400 FAILED_PRECONDITION. {'error': {'code': 400, 'message': 'The File cxgja95z0ak1 is not in an ACTIVE state and usage is not allowed.', 'status': 'FAILED_PRECONDITION'}}
```


## 0.1.4


- Add readme ([#2](https://github.com/mikonapoli/gaspare/issues/2))
- Fix `imagen` method not being exported


## 0.1.3

### New Features

- Add Gemini 2.5 Pro Preview ([#5](https://github.com/mikonapoli/gaspare/issues/5))
  - This will require restructuring the pricing functions, since the model's cost is based on prompt length (but with a different threshold than Gemini 1.5)



## 0.1.2

* BUG Fix: You can now `from gaspare import *`

## 0.1.0

INITIAL RELEASE

* Easy client and chat interface
* Multimodal input and output
* Easy handling of Youtube links
* Tool handling enhanced by docments
* Claudette interface compatibility
* Toolloop
* And more...

