# Question 1
For the low pass:
$H_{LP}=\frac{V_{LP}}{V_i}(s)=\frac{P(s)}{Q(s)}=\frac{1}{1+s(R_1C_1+(R_2+R_2)C_2+s^2R_1R_2C_1C_2}$

For the high pass:
$H_{HP}=\frac{V_{HP}}{V_i}(s)=\frac{P(s)}{Q(s)}=\frac{R_3R_4C_3C_4s^2}{1+s(R_3(C_3+C_4)+R_4C_4)+s^2R_3R_4C_3C_4}$

For the band pass:
$H_{BP}(s)=\frac{V_{BP}}{V_i}(s)=\frac{P(s)}{Q(s)}\frac{R_5C_5s}{1+s(R_5(C_5+C_6)+R_6C_6)+s^2R_5R_6C_5C_6}$

# Question 2
Since $f_1=f_2=f_3=2$kHz and $f_4=f_5=F-6=15$kHz
We choose $C_1=C_3=C_5=10$nF and $C_2=C_4=C_6=1$ nF

For the low pass:
$H_{LP}(s)=\dfrac{1}{1+s\!\left(R_1C_1+(R_1+R_2)C_2\right)+s^2R_1R_2C_1C_2}$
Gives:
$R_1C_1+(R_1+R_2)C_2=\frac{1}{2\pi f_1}+\frac{1}{2\pi f_2},\qquad R_1R_2C_1C_2=\frac{1}{2\pi f_1 2\pi f_2}$
Plugging in the [[Capacitors]]:
$R_1=7$k and $R_2=12$k

For the high pass:
$H_{HP}(s) = \frac{s}{s+2\pi f_3}\cdot\frac{s}{s+2\pi f_4}= \frac{s^2}{(s+2\pi f_3)(s+2\pi f_4)}$
Gives
$(C_3{+}C_4)R_3+C_4R_4=\frac{1}{2\pi f_3}+\frac{1}{2\pi f_4}$ and $C_3C_4R_3R_4=\frac{1}{(2\pi f_3)(2\pi f_4)}$
So
$R_3=7$k and $R_4=12$k

For the band pass:

$R_5=\frac{1}{2\pi f_5\,C_5}$ and $R_6=\frac{1}{2\pi f_6\,C_6},$
and
$R_5(C_5{+}C_6)+R_6C_6=\frac{1}{2\pi f_5}\!\left(1+\frac{C_6}{C_5}\right)+\frac{1}{2\pi f_6}$
So $R_5=8$k and $R_6=11$k

# Question 4
$V_{LP}(t)=0.15\sin(2\pi\cdot8000 t -104\degree)$
$V_{HP})(t)=0.32\sin(2\pi\cdot8000t+76\degree)$
$V_{BP}(t)=0.6\sin(2\pi\cdot8000t-14\degree)$
