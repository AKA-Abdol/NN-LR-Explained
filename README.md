# Neural Network Regression

## dataset
for a regression task, the input and output range matters. you need to consider that torch supports only `float64` at most. So when your output data is bigger than range of float64 you should consider other approaches to use losses.

## loss
the best loss for regression problems is absolutely the `MSE` but you also cal use `L1` loss. The `L1` loss has some considerations: 
- it can deactivate some neurons during training
- for bigger output data is only option
- loss following is different with MSE

## Batch Normalization and Dropout
These two options are not valid in a regression task. You have to ouput strict values not scale-invariant values. so the dropout activates all neurons as others so it over/underestimate. When using Batch Normalization
you have to use bigger batch sizes, it takes time and doesn't converge to global minima. also normalization over batches it may lose some data. it may make model converge faster but in other tasks not regression. the data is not spatial or scale-invariant.

## Batch size
big batch sizes make model to the local minimas. not too low batch size for stochasticness, not too big batch size to really traverse the are of optimization.

## Schedulers
it's really good to consider usage of schedulers. Your model complexity and capacity show you how to schedule.

## Bias vs. Variance
consider more complex models converge slower and may not converge also. enough depth and width for models is needed.

## scaling input vs output
when you scale down outputs, for lower values you are considering less errors than higher values. your error is multiplied by the scaledown factor finally. the input scaling doesn't that much matters. in classification tasks it's much important than in regression task.