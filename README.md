This is the **Chainer** implementation for the paper [The Lottery Ticket Hypothesis: Training Pruned Neural Network Architectures](https://arxiv.org/abs/1803.03635).

#### XOR
`python xor.py --hidden 8 4 2 --strategy pro --iter 1000 --epoch 10000 --minloss 1e-7 --patient 7`

- hidden: Number list for the hidden layers.
- strategy: Prune strategy. It is 'in' or 'out' or 'pro'.
- iter: Number of iterations for each number of hidden layer.
- epoch: Number of epochs for one iteration.
- minloss: Minimal change of loss for early stopping.
- patient: Counts to stop.

One result of the above command is below.
```
100 Iterations
H 8: DB 1.00, ZL 0.00
H 4: DB 0.89, ZL 0.00
H 2: DB 0.71, ZL 0.00
```

One result of `--hidden 8 6 4 2` is below.
```
100 Iterations
H 8: DB 0.98, ZL 0.00
H 6: DB 0.97, ZL 0.00
H 4: DB 0.89, ZL 0.00
H 2: DB 0.75, ZL 0.00
```

#### MNIST
`python mnist.py --percent 40 40 --iter 50000 --minacc 1e-3 --patient 5`

- percent: Percentage list to shrink.
- iter: Number of iterations.
- minacc: Minimal change of accuracy for early stopping.
- patient: Counts to stop.

One result of the above command is below.
```
100%: ITER 1534, TIME 6.62s, ACC 0.9418000983
60%: ITER 1170, TIME 4.70s, ACC 0.9338000821
36%: ITER 1612, TIME 6.42s, ACC 0.9429000020
```
