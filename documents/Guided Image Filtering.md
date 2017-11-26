## Guided Image Filtering

### Guided Filter : An explicit image filtering

### Definitions

- A guidance image $I$
- An input image $p$
- An output image $q$

The filtering output in a general filter at a pixel $i$ is expressed as a weighted average:
$$
q_i = \Sigma_j{W_{ij}(I)p_j}
$$
where $i,j$ are pixel indexes.

The key assumption of the guided filter is a local linear model between the guidance $I$ and the filter output $q$. We assume that $q$ is linear transformation of $I$ in a window $w_k$ centered at the pixel $k$ :
$$
q_i = a_kI_i+b_k, \forall i \in w_k
$$
where $(a_k,b_k)$ are some linear coefficients assumed to be constant in $w_k$.

To calculate $(a_k,b_k)$ , we minimize the difference between $q$ and the filter input $p$ .
$$
E(a_k,b_k) = \Sigma_{i\in w_k}((a_kI_i+b_k-p_i)^2+\epsilon a_k^2)
$$
Solution to eq(4) is
$$
a_k = \frac{\frac{1}{|w|}\Sigma_{i\in w_k}I_ip_i-\mu \bar{p_k}}{\sigma _k^2+\epsilon}
$$

$$
b_k = \bar{p_k}-a_k\mu _k
$$

$\mu _k$ and $ \sigma_k ^ 2$ are the mean and variance of $I$ in $w_k$, $\bar{p_k}=\Sigma_{i\in w_k}p_i$ is the mean of $p$ in $w_k$ .

After computing ($a_k, b_k$) for all patches $w_k$ in the image, we compute the filter output by:
$$
q_i = \frac{1}{|w|}\Sigma_{k:i\in w_k}(a_kI_i+b_k)
$$
