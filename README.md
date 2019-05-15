import numpy as np
from numpy import pi,sin,cos,exp

L = 500*1e3
alpha= 0.8
t = 0.9

def E_t1(alpha,t,x):
    theta =  2*pi*1.44*L/x
    return abs((-alpha+t*exp(-1j*theta))/(-alpha*t+exp(-1j*theta)))

fig = plt.figure(figsize=(8,8*0.618))

x = np.linspace(1520,1570,500)
plt.plot(x,np.real(E_t1(alpha,t,x)**2))

plt.xlabel('Wavelength(nm)')
plt.ylabel('Output')
plt.show()

fig.savefig(r'C:\Users\1193117569@QQ.COM\Desktop\liyuqi\fig1.svg'
,dpi=600,format='svg', facecolor=fig.get_facecolor())
