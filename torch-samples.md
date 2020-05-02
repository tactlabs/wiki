# Torch Samples

**Note:** tbw



Check cuda available
```
import torch

torch.cuda.is_available()
```






```
import torch
from torch.autograd import Function

class Exp(Function):

  @staticmethod
  def forward(ctx, i):
    result = i.exp()
    ctx.save_for_backward(result)

    return result

  @staticmethod
  def backward(ctx, grad_output):
    result, = ctx.saved_tensors()

    return grad_output * result

input = torch.rand(2, 2)

output = Exp.apply(input)

print(output)
```






```

```






```

```






```

```






```

```






```

```






```

```






```

```






```

```






```

```






```

```






```

```






```

```






```

```






```

```






```

```






```

```






```

```






```

```






```

```






```

```






```

```






```

```






```

```






```

```






```

```






```

```






```

```






```

```

# Ref :

  * []()
