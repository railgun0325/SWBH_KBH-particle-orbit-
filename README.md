# SWBH_KBH-particle-orbit-
关于对施瓦西黑洞以及克尔黑洞周围测试粒子数值计算的代码  
使用ADM分解处理之后的运动方程来计算SWBH以及KBH周围的粒子轨道  
## SWBH_orbit 
施瓦西黑洞周围的轨道可以正常计算
这里的初期值是 ${r,\theta,\varphi,u_r,r_{\theta},u_{\varphi}}$ ，我们可以将 $\theta$ 设置为 $\frac{\pi}{2}$ ,并令 $\varphi,u_r,r_{\theta}$ 的值都为0。
我们给定对应的轨道参数E和L，这个时候通过径向的运动方程 $$r^4 {u_r}={E}^2 r^4-\left(L^2+r^2\right) \left(r^2-r {r_s}\right)$$ 解出r的值，两个解分别对应轨道的远星点半径和近星点半径，这两个值都可以作为初始值使用；这个时候 $u_{\varphi}$ 的值等于L。将初始值 ${r,\frac{\pi}{2},0,0,0,u_{\varphi}}$ 输入接下来就可以进行轨道计算了。

## Kerr Orbit
类似的也可以通过	$$\rho u^r = \sqrt{ \left[ E(r^2 + a^2) - a L \right]^2 - \Delta \left[ r^2 + (L - a E)^2 \right] }$$ 解出对应的初期值，当然这里的代码有问题，并不能得到正确的轨道。可以使用KerrGeoPy来计算这里的轨道。
