# 🛰️ Progiciel Expert : GeoIRPI v5.7
## Direction de l'Environnement — Wilaya de Tizi Ouzou
### Modélisation Géo-Relationnelle Spatiale de l'Indice IRPI par Approche de Screening Prudencielle Hybride

Ce dépôt présente le cadre algorithmique et la structure de données du modèle d'évaluation de la sécurité industrielle déconcentrée à l'échelle de la commune de Larbaâ Nath Irathen [Local].

---

### 🔬 1. Formalisation Mathématique et Modèle Source
L'évaluation de l'Index de Risque Probabiliste Intégré ($\text{IRPI}_{\text{Spatial}}$) évalue le potentiel de danger source à partir de l'énergie totale libérable par le stockage, modélisé par une relation non compensatoire indexée sur la masse de stockage confinée réelle ($M_{\text{kg}}$) et l'enthalpie spécifique de la substance [Calcul] :

$$\Phi_{\text{Danger}} = \log_{10} \Big( M_{\text{kg}} \times \Delta H_{\text{Substance (MJ/kg)}} \Big)$$

Conformément aux principes de la mécanique des fluides régissant les ondes de détonation tridimensionnelles (explosions de gaz ou de vapeurs confinées), le rayon d'effet létal thermodynamique induit par l'onde de choc (surpression accidentelle) est évalué selon la loi de mise à l'échelle de Hopkinson-Cranz (loi de cubication) [Calcul] :

$$R_{\text{Thermodynamique}} = K \times M_{\text{kg}}^{1/3}$$

*Où $K$ est un coefficient empirique de surpression fixé par les standards internationaux (généralement $K = 5$ pour le seuil des effets létaux significatifs de 300 mbar, évitant toute surévaluation aberrante).*

Afin de neutraliser les pathologies de saturation visuelle des moniteurs sur l'interface graphique de l'APC, le moteur visuel applique une réduction homothétique d'échelle d'un facteur de dix, découplant le flux de calcul réel du rendu de l'écran [Calcul] :

$$R_{\text{Affichage Écran}} = \frac{R_{\text{Thermodynamique / Légal}}}{10}$$

---

### 📐 2. Méthodologie du Maillage SIG Tri-Cartes et Seuils Internationaux

Le logiciel opère la superposition spatiale (*Map Overlay*) de trois cartes locales décentralisées à l'aide d'une jointure relationnelle de Niveau 2 ($\bowtie$) s'exécutant sur l'identifiant univoque de l'installation ($\text{ID\_ICPE}$) [Calcul] :

$$\mathcal{S}_{\text{APC}} = \mathcal{H}_{(0..1)} \ \Big( \pi_{\text{Axes}} \ \big( \text{Carte}_{\text{ICPE}} \ \bowtie \ \text{Carte}_{\text{Énergie}} \ \bowtie \ \text{Carte}_{\text{Villages}}\big) \Big)$$

Toute violation géométrique constatée par le croisement de la couche industrielle (capacités de stockage), de la couche énergétique (canalisations Sonelgaz) et de la couche anthropique déclenche l'édition automatisée d'une notification de rejet motivée ou d'un arrêté d'autorisation [Finance, Calcul].

En l'absence de rayons fixes généralisés dans la législation nationale, le système expert applique une **approche prudencielle hybride**. Il intègre les distances guides de sécurité issues des standards internationaux (recommandations *Seveso III / US EPA / IChemE*) comme valeurs de pré-diagnostic par défaut (*Fallback*), modulables selon la classe de l'installation [Calcul] :
* **100 mètres (Seuil de vigilance bas) :** Appliqué par défaut pour la couche anthropique (habitations) sur les petites installations à faible potentiel de danger (équivalent régime de Déclaration APC).
* **500 mètres (Seuil de sécurité intermédiaire) :** Zone tampon minimale par défaut pour les établissements de taille moyenne présentant des risques d'effets thermiques ou toxiques modérés (équivalent Autorisation de Wilaya).
* **1500 mètres (Périmètre d'exclusion majeur) :** Rayon d'isolement par défaut appliqué aux complexes industriels à haut potentiel de dangers ou à effets dominos (équivalent Autorisation Ministérielle / Seuil Haut).

Ces valeurs de référence de screening sont écrasées dynamiquement dès l'injection des rayons d'effets calculés spécifiquement dans l'Étude de Dangers (ED) de l'établissement [Calcul].

---

### ⚖️ 3. Formalisme Booléen et Double Verrou de Contrôle
L'évaluation finale des demandes d'implantation (Titre 3) s'exécute à travers une fonction logique binaire d'homologation administrative, interdisant toute tolérance humaine discrétionnaire lors de l'instruction [Finance, Calcul] :

$$\text{Verdict}_{\text{Final}} = \mathbf{1}_{\text{Droit\_Algérien}} \times \mathbf{1}_{\text{Expertise\_Technique}}$$

#### A. Le Verrou Légal Exécutoire (Souveraineté Nationale)
La décision administrative de délivrance ou de rejet de l'acte d'urbanisme (Décret exécutif n° 15-19) est asservie de manière exclusive à la conformité aux décrets algériens n° 07-144 (servitude de 150 mètres des gazoducs Sonelgaz) et n° 06-198 (rayons de la nomenclature) [Local, Finance] :

$$\mathbf{1}_{\text{Droit\_Algérien}} = \sigma_{(D_{\text{Gaz}} \ge 150) \, \wedge \, (D_{\text{Taddart}} \ge \text{Rayon}_{\text{Rubrique}})}$$

#### B. Le Module d'Expertise Subsidiaire (Consultatif)
Les distances guides internationales interviennent à titre de garde-fou. Toute intersection d'une infrastructure avec les périmètres guides suspend le visa d'engagement à la production d'une Étude de Dangers (ED) spécifique validée par la commission technique [Calcul].

---
*Documentation technique de projet — Conforme au cadre réglementaire en vigueur au sein de la République Algérienne Démocratique et Populaire.*
