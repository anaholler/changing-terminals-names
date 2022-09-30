# changing-terminals-names

[20:38, 12/09/2022] Unb Yan: strifractorrr
[20:41, 12/09/2022] Unb Anderson: ahh
[20:41, 12/09/2022] Unb Anderson: os pacotes
[20:41, 12/09/2022] Unb Anderson: require(phytools)
require(ape)

#arvore filogenética
treefull<-read.tree("EXEMPLOARVOREFILOGENETICA.tre")
treefull
#dados
dat <- read.csv("PLANILHACOMOSNOMESDOSTERMINAIS.csv", sep = ";", row.names = 1)
rownames(dat)

#conferir se os terminais batem com a arvore
all(rownames(dat)%in%treefull$tip.label)

#cortar a arvore
tree<-drop.tip(treefull,which(treefull$tip.label%in%rownames(dat)==FALSE))

#Reordene os terminais para serem congruentes com os apices da arvore
dat<-dat[tree$tip.label,]

#checar congruencia
all(rownames(dat)==tree$tip.label)

rownames(dat)
tree
