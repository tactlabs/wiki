# Torch Samples

**Note:** Basics Torch Samples come here



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





Simple Jacobian
```
import torch
from torch.autograd.functional import jacobian

def exp_reducer(x):

  return x.exp().sum(dim = 1)

inputs = torch.rand(2, 2)

print(inputs)

jacobian(exp_reducer, inputs)

jacobian(exp_reducer, inputs, create_graph = True)

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
