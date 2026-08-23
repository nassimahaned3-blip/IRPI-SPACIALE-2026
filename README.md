GeoIRPI-Wilaya
latex\documentclass[12pt,a4paper]{article}
\usepackage[utf8]{inputenc}
\usepackage[french]{babel}
\usepackage[T1]{fontenc}
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
\usepackage{geometry}
\usepackage{booktabs}
\usepackage{hyperref}

\geometry{top=2.5cm, bottom=2.5cm, left=2.5cm, right=2.5cm}

\begin{document}

\begin{center}
    \large\bfseries RÉPUBLIQUE ALGÉRIENNE DÉMOCRATIQUE ET POPULAIRE \\
    \vspace{0.3cm}
    \small\bfseries WILAYA DE TIZI OUZOU -- DIRECTION DE L'ENVIRONNEMENT \\
    \vspace{1cm}
    \Large\bfseries RÉSUMÉ THÉORIQUE DU MÉMOIRE DE MASTER \\
    \vspace{0.5cm}
    \large\itshape Modélisation Géo-Relationnelle de l'Indice IRPI et Convergence des Cartes de Servitudes Énergétiques au Niveau Communal
\end{center}

\vspace{1.5cm}

\section{Introduction et Problématique Territoriale}
La gestion déconcentrée de la sécurité industrielle au sein de la Wilaya de Tizi Ouzou est soumise aux contraintes physiques du relief montagneux de Kabylie. L'imbrication des Installations Classées pour la Protection de l'Environnement (ICPE) à proximité immédiate des tissus urbains villageois (\textit{Taddart}) et des infrastructures énergétiques exige l'instauration d'un contrôle spatial strict. La présente étude démontre la viabilité d'un Système d'Information Géographique (SIG) communal autonome, capable d'auditer la conformité des implantations industrielles sans dépendance vis-à-vis d'un réseau centralisé national, en appliquant le principe de l'inversion de la charge de la donnée logistique.

\section{Le Continuum Réglementaire et Disjoncteurs Spatiaux}
L'architecture logicielle du système expert intègre l'ensemble de la législation souveraine algérienne régissant les distances de sécurité et les couloirs de servitudes inconstructibles. Le moteur de contrôle applique de manière déterministe six barrières juridiques et physiques coordonnées par une clause restrictive relationnelle :
\begin{enumerate}
    \item \textbf{Décret présidentiel n° 07-144 :} Fixation d'une zone d'étanchéité absolue de $150$~mètres de part et d'autre des canalisations de transport de gaz haute pression.
    \item \textbf{Décret exécutif n° 11-204 :} Établissement d'un couloir de servitude de $100$~mètres autour des pipelines de transport d'hydrocarbures liquides et liquéfiés (GPL phase liquide).
    \item \textbf{Arrêté interministériel du 14 juin 2011 (12 Rajab 1432) :} Délimitation dynamique des distances de sécurité du réseau de distribution Moyenne Tension (MT - 30~kV), fixées à $15$~mètres en zone rurale (conducteurs nus) et ramenées à $3$~mètres en zone urbaine consolidée (câbles isolés torsadés).
    \item \textbf{Décret exécutif n° 11-171 :} Imposition d'un périmètre d'isolement et de protection thermique de $5$~mètres autour des postes de transformation électrique (cabines et poteaux Sonelgaz).
    \item \textbf{Décret exécutif n° 06-198 :} Fixation de la nomenclature des ICPE et indexation des rayons légaux d'affichage d'enquête publique selon la classe d'activité ($100$~m pour le régime de Déclaration APC, $500$~m pour l'Autorisation de Wilaya, et $1500$~m pour le niveau Ministériel).
    \item \textbf{Décret exécutif n° 15-19 :} Cadre procédural suprême fixant les modalités d'instruction et de délivrance du Permis de Construire (PC) au niveau du guichet unique communal.
\end{enumerate}

\section{Formalisation Mathématique et Modèle Homothétique}
Le calcul de l'Index de Risque Probabiliste Intégré ($\text{IRPI}_{\text{Spatial}}$) repose sur une fonction produit non compensatoire de type Cobb-Douglas, indexée sur l'effet multiplicateur de la masse de stockage confinée réelle ($M_kg$) :
\begin{equation}
    \Phi_{\text{Danger}} = \log_{10} \Big( \text{Masse}_{\text{Stockée (kg)}} \times \text{Enthalpie}_{\text{Substance (MJ/kg)}} \Big)
\end{equation}
Le rayon de danger d'effet létal thermodynamique induit par l'onde de choc s'évalue selon la loi physique des gaz :
\begin{equation}
    R_{\text{Thermodynamique}} = 15 \times \sqrt[3]{\text{Masse}_{\text{Stockée (kg)}}}
\end{equation}
Afin de neutraliser les pathologies de saturation visuelle des moniteurs sur l'interface graphique de l'APC, le moteur visuel applique une réduction homothétique d'échelle d'un facteur de dix, découplant le flux de calcul réel du rendu de l'écran :
\begin{equation}
    R_{\text{Affichage Écran}} = \frac{R_{\text{Thermodynamique / Légal}}}{10}
\end{equation}

\section{Méthodologie du Maillage SIG Tri-Cartes}
Le logiciel opère la superposition spatiale (\textit{Map Overlay}) de trois cartes locales décentralisées à l'aide d'une jointure relationnelle de Niveau 2 ($\bowtie$) s'exécutant sur l'identifiant univoque de l'installation ($\text{ID\_ICPE}$) :
\begin{equation}
    \mathcal{S}_{\text{APC}} = \mathcal{H}_{(0.1)} \ \Big( \pi_{\text{Axes}} \ \big( \text{Carte}_{\text{ICPE}} \ \bowtie \ \text{Carte}_{\text{Énergie}} \ \bowtie \ \text{Carte}_{\text{Villages}}\big) \Big)
\end{equation}
Toute violation géométrique constatée par le croisement de la couche industrielle (capacités de stockage), de la couche énergétique (canalisations Sonelgaz) et de la couche anthropique (seuil des $100$~mètres par rapport aux habitations des villages) déclenche l'édition automatisée d'une notification de rejet motivée ou d'un arrêté d'autorisation, garantissant une régularité, une transparence et une orthodoxie administrative d'une exactitude absolue.

\end{document}
