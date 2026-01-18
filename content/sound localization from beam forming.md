---
{"publish":true,"created":"2025-12-30T16:55:08.391+05:45","modified":"2025-12-30T16:58:11.746+05:45","cssclasses":""}
---

TODO: Still many unknowns but we might have a good base to start with. 

> [!Note]
>This assumes the wave are planar otherwise beam forming won't work 

Let's start with circular microphones. 
![[attachments/Pasted image 20251230154033.png]]
Let us suppose $M$ microphones at known position $p_i \in \mathbb{R}^2$ or $\mathbb{R} = \{(x,y) | x \in \mathbb{R} , y \in \mathbb{R}\}$
Our goal is to estimate where the sound is coming from.  First we assume that sound that we are getting is planar. This means the speaker is far away that sound is |||||||| instead of ))))))). 
$$
\tau_i = \tau_o - \frac{1}{c}P_i^{\top}u
$$
-	where $T_o$ time at which wavefront hits the reference point at the center. This is not required as it cancels out. as we are doing $\tau_i - \tau_j$
-	$u = \begin{bmatrix} sin\theta && cos\theta\end{bmatrix}$ which is unit direction of arrival. angle theta is made between source and the speaker
-	$P_i^{\top}$ = $\begin{bmatrix} Rcos\phi_i \\ Rsin\phi_i \end{bmatrix}$ where $\top$ is transpose
- $P_i^{\top}.u$ is just projection of direction u. Geometrically it's $||P_i||cos(\phi_i-\theta)$ 
- since we are working on Time = distance / velocity we get $c$

![[attachments/Pasted image 20251230162333.png]]
Now we don't even need $\tau_o$ because we are doing $\tau_i - \tau_j$  and what we want is $u$ or $\theta$.

Now the new equation for microphone signal
$$ x_i(t)=s\bigl(t-\tau_i\bigr)+\sum_{k} n_k\bigl(t-\tau_{ik}\bigr) $$
$x_i(t)$: signal recorded at microphone $i$ at time $t$.
$s(t)$: desired (target) source waveform (e.g., the speaker we want to keep).
$\tau_i$: propagation delay from the desired source to microphone $i$
	(under the planar-wave model, $\tau_i=\tau_0-\frac{1}{c}\mathbf{p}_i^{\mathsf T}\mathbf{u}$).
$n_k(t)$: waveform of the $k$-th interfering source (another speaker/noise source).
$\tau_{ik}$: propagation delay from interferer $k$ to microphone $i$.
$\sum_{k}$: sum over all interfering sources $k$ present in the environment.

Now for the  beam forming
$$
y(t)=\sum_{i=1}^{M} w_i\,x_i\!\left(t+\hat{\tau}_i(\mathbf{u})\right)
$$
$y(t)$: beamformer output signal after spatial filtering.
$M$: total number of microphones in the array.
$w_i$: weight applied to microphone $i$
	(for delay-and-sum beamforming, $w_i=\frac{1}{M}$).
$x_i(t)$: signal recorded at microphone $i$.
$\hat{\tau}_i(\mathbf{u})$: predicted propagation delay for microphone $i$. The hat is present because this is predicted
	assuming the sound arrives from direction $\mathbf{u}$
	(computed from array geometry).
$\mathbf{u}$: unit direction-of-arrival vector of the desired source.
Each microphone records a time-shifted version of the same desired signal:
	$x_i(t)=s(t-\tau_i)$.
	
The time shifts $\tau_i$ depend on the spatial position of the microphone relative to the incoming wavefront. By delaying each $x_i(t)$ by $\hat{\tau}_i(\mathbf{u})$, signals arriving from direction $\mathbf{u}$ are aligned in time. Once aligned, the desired signal adds constructively across microphones, increasing its amplitude. Signals arriving from other directions are misaligned and therefore add destructively, resulting in attenuation.

