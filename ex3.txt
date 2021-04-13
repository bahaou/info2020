def verif(S):                                                #DEf FN verif(S:chaine):booleen
    v = True                                                    #Booleen v <- vrai
    for i in range(len(S)):                                     #pour i de 1 a long(S):
        if (not S[i] in ['H','G','B','D']):                          #si (non S[i] dans ['H','G','B','D'] )alors
            v = False                                                       #v<-faux
                                                                        #finsi
                                                                #finpour
    return v                                                    #verif <- v
                                                            #fin verif
                


def saisir():                                                 #def PROC saisir(NL,NC,L,C:entier,S:chaine)
    while(True):                                                 #repeter
        NL=int(input('donner NL'))                                  #ecrire("donner NL")
                                                                    #lire(NL)
        if ( 0< NL and NL <=100):                               #jusqu'a NL dans [1..100]
            break
    while(True):                                                 #repeter
        NC=int(input('donner NC'))                                  #ecrire("donner NC")
                                                                    #lire(NC)
        if ( 0< NC and NC <=100):                               #jusqu'a NC dans [1..100]
            break
    while(True):                                                 #repeter
        L=int(input('donner L'))                                    #ecrire("donner L")
                                                                    #lire(L)
        if ( 0< L and L <=NL):                                   #jusqu'a L dans [1..NL]
            break
    while(True):                                                 #repeter
        C=int(input('donner C'))                                    #ecrire("donner C")
                                                                    #lire(C)
        if ( 0< C and C <=NC):                                   #jusqu'a C dans [1..NC]
            break

    while(True):                                                 #repeter
        S=input("donner S")                                         #ecrire("donne S")
                                                                    #lire(S)
        if verif(S):                                              #jusqua verif(S) = vrai
            break
    return [NL,NC,L,C,S]
NL,NC,L,C,S=saisir()
#NL  entier  nombre de ligne
#NC  entier  nombre de colone
#L   entier  position ligne du robot
#C   entier  position colone du robot
#S   chaine  sequence a parcourire


def coder(NL,NC,L,C,S):                                            #def PROC coder(NL,NC,L,C;entier,S,R:chaine)
    i = 0                                                               #integer i <- 0
            
    while(True):                                                        #repeter
                                                                             #i<- i+1
        if S[i]== 'H':                                                       #si S[i] = 'H' faire
            L=L-1                                                               #L=L-1
        if S[i]== 'B':                                                       #si S[i] = 'H' faire
            L=L+1                                                               #L=L+1
        if S[i]== 'G':                                                       #si S[i] = 'G' faire
            C=C-1                                                               #C=C-1
        if S[i]== 'D':                                                       #si S[i] = 'H' faire
            C=C+1                                                               #C=C+1
        i=i+1                                                                   
        if L<1 or L > NL or C < 1 or C > NC or i == len(S)  :          # jusqua  L<1 ou L > NL ou C < 1 ou C > NC i = long(S)
            break
    if i==len(S) :                                                   #si i=long(S) alors
        print("Je suis a la position({},{})".format(L,C))                   #R<-"Je suis a la position"+L+","+C+")"
    else:                                                               #sinon alors
        print("Attention cas de depassement cause par le pas N°",i)       #R<- "Attention cas de depassement cause par le pas N°"+i)

coder(NL,NC,L,C,S)

            
    

            
        
    
