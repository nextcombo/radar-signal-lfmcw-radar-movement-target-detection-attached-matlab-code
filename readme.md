# Radar Signal: LFMCW Radar Movement Target Detection [Attached MATLAB Code]

MATLAB Simulation Results:  
MATLAB Code:  
Partial code display:
% Title: The System of LFMCW Radar\n% Attenna Arrays:    4*32\n% Author: Ding Jieru\n% Date:    2019-11-24\nclear all; clc; close all; \nfc=77e9; \nj=sqrt(-1); \nB=1e9; \nc=3e8; \nFs=10e6; \nT=80e-6; % PRT \nPRF=1/T; \nK=B/T; \nR=[10,50,9]; % Target distance; \nV=[100,1,-100]; % Target speed; m/s\nTheta=[9,10,9]; \nlambda=c/fc; \nd=lambda/2; % indicates the spacing between oscillators % Target Doppler Frequency % Signal-to-noise ratio % In which, L represents the number of sine waves. % Sample points number \nt_n=0:1/Fs:T; \nN=length(t_n); \nCPN=60; \ndn=zeros(CPN,N,L); \nQ=length(R); \n%%   Generation The Data Cube\nfor l=0:L-1\n    for cpn=1:CPN\n        for q=1:Q\n            x(q,:)=exp(2*j*pi*(((2*K*R(q))/c+(2*K*V(q)*cpn*T)/c)*t_n+2*V(q)/lambda*cpn*T+2*fc*R(q)/c+d/lambda*l*sind(Theta(q)))); \n        end\n        dn(cpn,:,l+1)=sum(x); \n        clear x\n    end\nend\ndn=awgn(dn,SNR); \nsave('Data_cube','dn'); \n%%    Test code \nsignal_Per_Array=dn(:,:,1); \nfigure; \nsubplot(211),plot([1:N],real(signal_Per_Array(1,:))); title('real part of ADC data'); \nsignal_Pc=fft(signal_Per_Array,2^(nextpow2(N)),2); \nsubplot(212); plot(abs(signal_Pc(1,:))); title(' Pluse Compression data'); \nfigure; \nsubplot(211); \nimagesc(abs(signal_Pc)); \ncolormap('jet'); colorbar; \nset(gca,'YDir','normal'); xlabel('Distance'); ylabel('CPN'); \nsignal_mtd=fft(signal_Pc,2^(nextpow2(CPN))); \ntitle('CPN Matrix'); \nsubplot(212)\nimagesc(abs(fftshift(signal_mtd,1))); colormap('jet'); colorbar; \nset(gca,'YDir','normal'); xlabel('Distance'); ylabel('velocity'); \ntitle('RD Matrix'); \n%%      Signal Processing \n

## Images

![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](01.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](02.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](03.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](04.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](05.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](06.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](07.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](08.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](09.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](10.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](11.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](12.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](13.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](14.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](15.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](16.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](17.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](18.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](19.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](20.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](21.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](22.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](23.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](24.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](25.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](26.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](27.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](28.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](29.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](30.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](31.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](32.jpg)
![(Radar Signal)LFMCW Radar Moving Target Detection [Attached MATLAB Code]](33.jpg)

<!-- PAYMENT_BLOCK -->

## Get this dataset

- Payment link (Stripe): [Buy now](https://buy.stripe.com/3cs8yP7sY87d0vu9AB)
- Payment QR code: ![Payment QR code](pay.png)

<!-- /PAYMENT_BLOCK -->
