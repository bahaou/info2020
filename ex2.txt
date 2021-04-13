def INCONNU(T,p1,p2):
    if p1 > p2:
        aux = p2
        p2=p1
        p1=aux
    S=0
    for i in range(p1,p2+1): #pour i de p1 a p2
        S=S+T[i-1]    #S=S+T[i]
    return(S)

def affiche_equilibre(T,n):
    vide = True                            #Boolen vide <- vrai
    for i in range(1,n-1):                 #pour i de 2 a n-1 faire
        S1=INCONNU(T,1,i)                       #S1<-INCONNU(T,1,i-1)
        S2=INCONNU(T,i+2,n)                     #S2<-INCONNU(T,i+1,n)
        if S1==S2:                              #si S1=S2 alors
            print(i+1)                              #ecrire(i)
            vide = False                            #vide <- faux
                                                #finsi

                                            #finpour
    if vide == True:                        #si vide = vrai alors
        print("Aucun point d'equilibre")        #ecrire("Aucun point d'equilibre")
                                            #finsi
                                            #fin affiche_equilibre
        



T=[-2,19,-8,-14,4,5,-4,3,-8,9]


affiche_equilibre(T,10)
