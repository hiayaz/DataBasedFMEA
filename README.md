# DataBasedFMEA
Data Based FMEA
CLC 
clear all
load ('DMCSP_2'); %load decision matrix, columns and rows describe attributes and observations, respectively. Last column is consist initial ranks of observations.
load('WSens.mat');%load weight vector for attributes
cb=[1 1 2 2 2];%give cost/benefit vector. Cost for 1 benefit for 2
DM=DMCSP;
W=WSens;
b=size(DM,1);
t=1;
DM=ABAC(DM,W,t,b,cb);
