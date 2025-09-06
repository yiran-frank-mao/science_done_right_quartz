**Def**  <i><u>Linear Time Invariant System</u></i>
Linear Time Invariant system is a linear function transformation $\mathcal{LRT}$ with invariant time defined by a Fourier pair: impulse response function $g(t)$ and a transfer function $G(\omega)$.
In real domain, the output function is given by:
$$ y_{\mathrm{out}}(t)=g(t)*y_{\mathrm{in}}(t)=\int_{-\infty}^{\infty}\!g(\tau)\,y_{\mathrm{in}}(t-\tau)\,d\tau $$
Specially, for delta impulse, we have $y_{\mathrm{out}}(t)=g(t)*\delta(t)=g(t)$
In Fourier domain, the output function is given by:
$$ Y_{\mathrm{out}}(\omega)=G(\omega)Y_{\mathrm{in}}(\omega) $$

**Prop**  For any input function $y_{\mathrm{in}}(t),z_{\mathrm{in}}(t)$ and the corresponding output function $y_{\mathrm{out}}(t),z_{\mathrm{out}}(t)$, we have following properties:
$$ \begin{aligned}
\mathcal{LTI}[y_{\mathrm{in}}(t)+z_{\mathrm{in}}(t)] = y_{\mathrm{out}}(t)+z_{\mathrm{out}}(t) \\ \mathcal{LTI}[y_{\mathrm{in}}(t+\tau)]= y_{\mathrm{out}}(t+\tau) 
\end{aligned}$$