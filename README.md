# FIR-FILTER-DESIGN
# EXP 4 c: Design-of-FIR-Digital-Filter-using-Hanning-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Hanning-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
close;
M=input('Enter the Odd Filter Length =');
Wc=input('Enter the Digital Cut off frequency =');
alpha=(M-1)/2;
for n=1:M
if (n==alpha+1) then
hd(n)=Wc/%pi;
else
hd(n)=sin(Wc*((n-1)-alpha))/(((n-1)-alpha)*%pi);
end
end
for n=1:M
W(n)=0.5-(0.5*cos((2*%pi*(n-1))/(M-1)));
end
h=hd.*W;
disp(h,'Filter Coefficients are');
[hzm,fr]=frmag(h,256);
subplot(2,1,1);
plot(2*fr,hzm);
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR LPF using Hanning Window');
hzm_dB=20*log10(hzm);
subplot(2,1,2);
plot(2*fr,hzm_dB);
xlabel('Normalized Digital Frequency W');
ylabel('Magnitude in dB');
title('Frequency Response of FIR LPF using Hanning Window');
```

# OUTPUT: 

<img width="757" height="712" alt="image" src="https://github.com/user-attachments/assets/75ec6f5e-d905-479e-9fbf-00eacc7bb2af" />
<img width="895" height="992" alt="image" src="https://github.com/user-attachments/assets/739c30a4-be1c-41af-a7ea-ae3c975280b3" />


# RESULT: 

Thus design of low pass FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
close;
M=input('Enter the Odd Filter Length =');
Wc=input('Enter the Digital Cut off frequency =');
alpha=(M-1)/2;
for n=1:M
if (n==alpha+1) then
hd(n)=1-Wc/%pi;
else
hd(n)=-sin(Wc*((n-1)-alpha))/(((n-1)-alpha)*%pi);
end
end
for n=1:M
W(n)=0.5-(0.5*cos((2*%pi*(n-1))/(M-1)));
end
h=hd.*W;
disp(h,'Filter Coefficients are');
[hzm,fr]=frmag(h,256);
subplot(2,1,1);
plot(2*fr,hzm);
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR HPF using Hanning Window');
hzm_dB=20*log10(hzm);
subplot(2,1,2);
plot(2*fr,hzm_dB);
xlabel('Normalized Digital Frequency W');
ylabel('Magnitude in dB');
title('Frequency Response of FIR HPF using Hanning Window');
```

# OUTPUT: 

<img width="752" height="717" alt="image" src="https://github.com/user-attachments/assets/9786bad4-2185-44ea-8200-5873e70793a6" />
<img width="531" height="612" alt="image" src="https://github.com/user-attachments/assets/3ac3ab18-de7a-4faa-be73-aa1dbe53363f" />


# RESULT: 
Thus design of HIGH pass FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
close;
M=input('Enter the Odd Filter Length =');
Wc=input('Enter the Digital Cut off frequency =');
Wc2=Wc(2);
Wc1=Wc(1);
alpha=(M-1)/2;
for n=1:M
if (n==alpha+1) then
hd(n)=(Wc2-Wc1)/%pi;
else
hd(n)=(sin(Wc2*((n-1)-alpha))-sin(Wc1*((n-1)-alpha)))/(((n-1)-alpha)*%pi);
end
end
for n=1:M
W(n)=0.5-(0.5*cos((2*%pi*(n-1))/(M-1)));
end
h=hd.*W;
disp(h,'Filter Coefficients are');
[hzm,fr]=frmag(h,256);
subplot(2,1,1);
plot(2*fr,hzm);
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR BPF using Hanning Window');
hzm_dB=20*log10(hzm);
subplot(2,1,2);
plot(2*fr,hzm_dB);
xlabel('Normalized Digital Frequency W');
ylabel('Magnitude in dB');
title('Frequency Response of FIR BPF using Hanning Window');
```
# OUTPUT: 

<img width="758" height="717" alt="image" src="https://github.com/user-attachments/assets/1263dc8b-fe38-490a-ae64-291e478395ef" />
<img width="717" height="631" alt="image" src="https://github.com/user-attachments/assets/994986ad-97bd-4d18-919f-813057e1c1e1" />


# RESULT: 
Thus design of BAND pass FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
close;
M=input('Enter the Odd Filter Length =');
Wc=input('Enter the Digital Cut off frequency =');
Wc2=Wc(2);
Wc1=Wc(1);
alpha=(M-1)/2;
for n=1:M
if (n==alpha+1) then
hd(n)=1-((Wc2-Wc1)/%pi);
else
hd(n)=(sin(Wc1*((n-1)-alpha))-sin(Wc2*((n-1)-alpha)))/(((n-1)-alpha)*%pi);
end
end
for n=1:M
W(n)=0.5-(0.5*cos((2*%pi*(n-1))/(M-1)));
end
h=hd.*W;
disp(h,'Filter Coefficients are');
[hzm,fr]=frmag(h,256);
subplot(2,1,1);
plot(2*fr,hzm);
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR BSF using Hanning Window');
hzm_dB=20*log10(hzm);
subplot(2,1,2);
plot(2*fr,hzm_dB);
xlabel('Normalized Digital Frequency W');
ylabel('Magnitude in dB');
title('Frequency Response of FIR BSF using Hanning Window');
```
# OUTPUT: 
<img width="755" height="722" alt="image" src="https://github.com/user-attachments/assets/76493892-7e59-465b-92cc-446bd58f2424" />
<img width="721" height="695" alt="image" src="https://github.com/user-attachments/assets/a3a83d15-0ba4-4252-8e45-bbe0c8a3dedb" />


# RESULT: 
Thus design of BAND STOP FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.
