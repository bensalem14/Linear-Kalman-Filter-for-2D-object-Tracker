# Linear-Kalman-Filter-for-2D-object-Tracker

**the System Model:**<br><br>
$x_k=F_{k-1}x_{k-1}+w_{k-1}$<br><br>

**the Observation Model:**<br><br>
$z_k=H_{k}x_{k}+v_{k}$<br><br>

**the Assumptions:**<br><br>
1)Gaussian error with 0 mean and covariance matrix<br><br>
$w_k \thicksim N(0,Q_k)$<br>
$v_k \thicksim N(0,R_k)$<br><br>
2)Time independent error <br><br>
$E(w_kw^T_j)=Q_k\delta_{k-j} $<br>
$E(v_kv^T_j)=R_k\delta_{k-j} $<br><br>
3)Uncorrelation of measurement noise with dynamical noise <br><br>
$E(w_kv^T_j)=0 $<br><br>

**the state vector:**<br><br>
$x_k={[p_x,p_y,v_x,v_y]}^T_k$<br><br>

**F matrix:**<br><br>

$[1 \quad 0 \quad \Delta t  \quad 0]$<br>
$[0 \quad 1 \quad 0 \quad \Delta t]$<br>
$[0 \quad 0 \quad 1 \quad 0]$<br>
$[0 \quad 0 \quad 0 \quad 1]$<br>
<br><br>
**noise input :**<br><br>
$w_k=[a_x,a_y,a_x,a_y]^T_k$<br>
$\sigma_{a}=\sigma_{a_x}=\sigma_{a_y}$<br>
<br><br>
**Q matrix :**<br><br>
$[\frac{1}{2}\Delta t^2 \quad 0 \quad 0 \quad 0 ]$<br>
$[ 0 \quad  \frac{1}{2}\Delta t^2 \quad 0 \quad 0 ]$<br>
$[ 0 \quad 0\quad  \quad \Delta t  \quad 0 ]$<br>
$[ 0 \quad 0\quad \quad  0\quad \Delta t  ]$<br>
<br><br>
we denote the a prori estimate or the forward estimate by f and the posteriori estimate the analysis estimate by a <br><br>
**prediction :**<br><br>
$x_k=Fx_{k-1}$<br>
$P_{f,k}=FP_{a,k-1}F^T+Q$<br>
<br><br>

**Innovation :**<br><br>
$z_k$ is our measurement vector<br>
$\tilde{y_k}=z_k - H_k \hat{x}_{f,k}$
<br><br>

**Innovation Covariance :**<br><br>
$S_k=H_k P_{f,k} H_k^T + R_k$
<br><br>

**Update**<br><br>

$\hat{x_{a,k}} = \hat{x}_{f,k} + K_k \tilde{y_k}$<br>

$P_{a,k}=(I-K_kH_k)P_{f,k}$<br>

$K_k=P_{f,k}H^T_kS_k^{-1}$<br>

$S_k=H_kP_{f,k}H^T_k+R_k$<br>
<br>


