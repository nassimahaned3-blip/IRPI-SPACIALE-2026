# 🛰️ Progiciel Expert : GeoIRPI v6.0
## Direction de l'Environnement — Wilaya de Tizi Ouzou
### Modélisation Géo-Relationnelle de l'Indice IRPI par Approche de Screening et Masse Équivalente TNT

Ce dépôt présente le cadre algorithmique et la structure de données du modèle d'évaluation de la sécurité industrielle déconcentrée à l'échelle de la commune de Larbaâ Nath Irathen [Local].

---

### 🔬 1. Formalisation Mathématique et Modèle Source Normalisé
L'évaluation de l'Indice de Gravité Potentielle ($\Phi_{\text{Danger}}$) quantifie le potentiel énergétique source disponible au sein du stockage, normalisé par une constante d'énergie de référence ($E_0 = 1$ MJ) pour assurer l'adimensionnalité de la fonction logarithmique [Calcul] :

$$\Phi_{\text{Danger}} = \log_{10} \left( \frac{M_{\text{kg}} \times \Delta H_{\text{Substance (MJ/kg)}}}{1 \text{ MJ}} \right)$$

Le calcul des ondes de surpression accidentelle obéit à la loi de cubication de Hopkinson-Cranz. Le modèle convertit la masse brute de produit en masse équivalente de TNT ($M_{\text{TNT}}$) en intégrant le rendement thermique de l'explosion ($\alpha = 0,1$) et l'enthalpie du TNT ($\Delta H_{\text{TNT}} = 4,69$ MJ/kg) [Calcul] :

$$M_{\text{TNT}} = M_{\text{kg}} \times \left( \frac{\Delta H_{\text{Substance}}}{4,69} \right) \times \alpha$$

$$R_{\text{Thermodynamique}} = K \times M_{\text{TNT}}^{1/3}$$

*Où $K$ est le coefficient empirique fixé par les standards internationaux ($K = 5$ pour le seuil des effets létaux significatifs de 300 mbar).*

Afin de garantir la sécurité publique et la sincérité de la prise de décision cartographique, le moteur visuel maintient une correspondance stricte d'échelle à 1:1 entre le rayon physique calculé au sol et le tracé vectoriel projeté sur le fond de carte du SIG [Calcul] :

$$R_{\text{Affichage}} = R_{\text{Thermodynamique}}$$

---

### ⚖️ 2. Verrou de Contrôle par Crochets d'Iverson
L'évaluation finale des demandes d'implantation (Titre 3) s'exécute à travers une fonction d'homologation administrative régie par les crochets d'Iverson, élimiant toute confusion avec l'algèbre relationnelle des bases de données [Finance, Calcul] :

$$\text{Verdict}_{\text{Final}} = \mathbf{1}_{\text{Droit\_Algérien}}$$

La décision de délivrance ou de rejet de l'acte d'urbanisme (Décret exécutif n° 15-19) est asservie de manière exclusive à la conformité aux décrets algériens n° 07-144 (servitude de 150 mètres des gazoducs Sonelgaz) et n° 06-198 (rayons d'isolement) [Local, Finance] :

$$\mathbf{1}_{\text{Droit\_Algérien}} = \left[ D_{\text{Gazoduc}} \ge 150\,\text{m} \,\,\wedge \,\, D_{\text{Taddart}} \ge R_{\text{Thermodynamique}} \right]$$

Toute violation de ces conditions géométriques fait tomber l'indicateur à 0, entraînant le rejet immédiat du dossier au guichet unique de la commune [Finance, Calcul].
