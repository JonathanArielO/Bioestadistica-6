# Bioestadistica-6
##Ej 1
###Turbiedad_1<-c(1.002,1.203,1.105,1.105,2.401,2.201,2.602,4.101,5.001,10.003,4.000,4.101,4.200,4.101,5.104,4.502,5.000,15.201,10.003,20.004,1.101,1.102,1.201,1.600,2.205,3.006,4.001,10.502)
###Turbiedad_2<-c(1.150,1.380,1.261,1.264,2.762,2.533,2.990,4.715,5.750,11.500,4.600,4.715,4.830,4.715,5.865,5.175,5.750,17.480,11.550,23.120,1.265,1.265,1.380,1.840,2.530,3.450,4.600,12.075)
###par(mfrow=c(2,1))
###hist(Turbiedad_1,col="lightgreen",ylab="Probabilidad",xlab="Medida de Turbiedad",main="Turbiedad Río 1",probability = TRUE)
###hist(Turbiedad_2,col="lightblue",ylab="Probabilidad",xlab="Medida de Turbiedad",main="Turbiedad Río 2",probability = TRUE)
###shapiro.test(Turbiedad_1)
###shapiro.test(Turbiedad_2)
###log_tur<-log(Turbiedad_1)
###log_tur_2<-log(Turbiedad_2)
###par(mfrow=c(2,1))
###hist(log_tur,col="lightgreen",ylab="Probabilidad",xlab="Medida de Turbiedad",main="Turbiedad Río 1",probability = TRUE)
###hist(log_tur_2,col="lightblue",ylab="Probabilidad",xlab="Medida de Turbiedad",main="Turbiedad Río 2",probability = TRUE)
###shapiro.test(log_tur)
###shapiro.test(log_tur_2)
####H0: La presencia de abejas es independiente del color de las flores.
####H1: Existe una asociación entre el color de la flor y la presencia de abejas.
###45+36
###24+83
###60+40
###45+24+60
###36+83+40
###Esperadas_BS<-(159/288)*81
###Esperadas_BS
###Esperadas_RC<-(129/288)*107
###Esperadas_RC
###Esperadas_RS<-(159/288)*107
###Esperadas_RS
###Esperadas_AC<-(129/288)*100
###Esperadas_AC
###Esperadas_AS<-(159/288)*100
###Esperadas_AS
###X2<-((45-36.3)^2/36.3)+((36-44.7)^2/44.7)+((24-47.9)^2/47.9)+((83-59.1)^2/59.1)+((60-44.8)^2/44.8)+((40-55.2)^2/55.2)
###X2
####Se rechaza H0 y se acepta la relación entre el color de las flores y la presencia de abejas.
###Con_abejas <-c(45,24,60)
###Con_abejas
###Sin_abejas<-c(36,83,40)
###Sin_abejas
###Presencia<-data.frame(rbind(Con_abejas,Sin_abejas))
###names(Presencia)<-c('Blancas','Rojas','Amarillas')
####H0: La presencia de abejas es independiente del color de las flores.
####H1: Existe una asociación entre el color de la flor y la presencia de abejas.
###chisq.test(Presencia)
#### Se rechaza H0
###pres<-(as.matrix(Presencia))
###barplot(pres,beside=TRUE,col=c("black","white"),legend=TRUE,ylab="Frecuencia"
##"Ej 2
###setwd("C:/Users/Laboratorio/Desktop/taller 6")
###list.files()
###tabaco<-read.csv("Tabaco.csv",header=TRUE,sep=";")
###head(tabaco)
###dim(tabaco)
###tc_tabaco<-table(tabaco$Adiccion,tabaco$Ejercicio)
###tc_tabaco
###par(mfrow=c(1,1),mar=c(5,5,4,6))
###barplot(tc_tabaco,main="Adicción al tabaco y ejercicio",xlab="Ejercicio semanal",ylab="Número de estudiantes",col=c("lightgreen","steelblue1","orange","red"),ylim=c(0,100),beside=TRUE,legend=rownames(tc_tabaco),args.legend=list(x='topright', bty='n', inset=c(-0.25,0)))
####H0: El nivel de consumo de tabaco es independiente del nivel de actividad física
####H1: Existe una asociación entre ambas variables
###chisq.test(tc_tabaco)
###tc2_tabaco<-cbind(tc_tabaco[,"Frecuentemente"],tc_tabaco[,"Nada"]+tc_tabaco[,"Poco"])
###tc2_tabaco
###chisq.test(tc2_tabaco)
####En ambos caso se acepta H0 (p-value="o"<0.5)
###tabaco2<-read.csv("Tabaco2.csv",header=TRUE,sep=";")
###tabaco2
###dim(tabaco2)
###tc_tabaco2<-table(tabaco2$Adiccion,tabaco2$Ejercicio)
###tc_tabaco2
###par(mfrow=c(1,1), mar=c(5,5,4,6))
###barplot(tc_tabaco2, main="Adicción al tabaco y ejercicio",xlab="Ejercicio semanal",ylab="Número de estudiantes",col=c("lightgreen","steelblue1","orange","red"),legend=rownames(tc_tabaco2),args.legend=list(x ='topright',bty='n', inset=c(-0.25,0)),ylim=c(0,500),beside=TRUE)
###chisq.test(tc_tabaco2)
####Se rechaza H0 (p-value=2.2*10^(-16))
