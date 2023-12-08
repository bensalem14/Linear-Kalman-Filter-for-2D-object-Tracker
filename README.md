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


