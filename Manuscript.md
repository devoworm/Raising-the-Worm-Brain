## Raising the Connectome: the emergence of neuronal activity and behavior in _C. elegans_

### Abstract
The differentiation of neurons and formation of connections between cells is the basis of both the adult phenotype and behaviors tied to cognition, perception, reproduction, and survival. Such behaviors are associated with local (circuits) and global (connectome) brain networks. A solid understanding of how these networks emerge is critical. Here, we provide a guided tour of early developmental events in the emerging connectome, defined here as the connectogenetic process. Connectogenesis includes associating cell identities with broader functional and developmental relationships. During this process, the transition from developmental cells to terminally differentiated cells is defined by the accumulation of traits that ultimately results in neuronal-driven behavior. The well-characterized developmental and cell biology of _C. elegans_ will be used to build a synthesis of developmental events that result in a functioning connectome. Developing a connectogenetic synthesis also enables the demonstration of a first-mover model of electrical connectivity. In a first-mover model of Stackleberg competition, potential pre- and post-synaptic relationships are shown to yield various strategies for establishing various types of electrical connections. By comparing these results to what is known regarding principles for establishing complex network connectivity, these  strategies are generalizable to other species and developmental systems. In conclusion, we will discuss the broader implications of this approach, as what is presented here informs an understanding of behavioral emergence and the ability to simulate related biological phenomena.

### Introduction
The field of connectomics has provided opportunities to view the structure and function of nervous systems in a new light. The proliferation of data for small connectomes such as those found in the nematode Caenorhabditis elegans allows us to study the connected nervous system at both the single cell and systems level (Berck et.al, 2016; Eichler et.al, 2017; Ko et.al, 2013). Emerging functional perspectives on genomic contributions (Barabasi and Barabasi, 2020) and statistical regularities (Takagi, 2017) of the connectome allow for a flexible, multiscale model of biology and behavior. This perspective will be used to identify associations between the various properties and behaviors of terminally-differentiated neurons and their presence at various points in embryogenesis. We propose a new term for this process: connectogenesis. An informatics approach will be employed to unify the individual steps of connectogenesis and reveal the systemic regularities that result in a functionally unified network. As we utilize multiple sources of data, a number of assumptions are made that might obfuscate the differences between various stages in life-history. For example, it is important to distinguish between the timing of events associated with the adult state of cells (such as gene expression) and the embryonic state of cells with the same identity (Hobert et.al, 2016). On the other hand, cellular state tends to be conserved when comparing development and adulthood. Therefore, based on these partial patterns of adult connectivity, generalizations can be made with respect to the structural and functional features of a developing connectome (Kaiser, 2017). 

To understand the sequential assembly of the developmental connectome further, we will introduce a first-mover model of cell-cell competition for establishing electrical connectivity. A dataset of synaptic connectivity (Witvliet et.al, 2020) will be used to establish strategies favored by individual cells that establish presynaptic and postsynaptic relationships. First-mover dynamics are based on the principle of Stackleberg competition (Simaan & Cruz, 1973), which is a competitive model of sequential actions. In the developmental biological context, first-movers have the advantage of not being directly subject to developmental contingencies (Morton, 1986). The first-mover model is meant to capture the process of growth, differentiation, and associated interactions defining the transition from emerging structure to organized function (Vogelstein et.al, 2019). The first-mover model of Stackleberg competition applied to developmental systems was first proposed in Stone et.al (2018), and is used here to represent the evolution of interactions between the emergence of newly-born neurons, asymmetric ion channel expression amongst bilateral pairs, and the formation of neural circuits. 

A parallel area of inquiry involves exactly when and under what conditions these terminally-differentiated neurons begin to produce organismal-level behaviors. It has been suggested that structural features emerge earlier in development than functional features (Cao et.al, 2016). As we will see, the first neuronal cells emerge well before the first synaptic connections between cells are established. In addition, the first goal-directed behaviors require electrical connections to be established between neuronal and muscle cells. Our contribution to this understanding is to flesh out the structure of this timing relative to differentiation events. This includes making connections between the terminal differentiation of specific neurons in development, their eventual functional identity, and the systems-level significance of this temporal process. These relationships help us understand the tempo and scope of connectogenesis relative to the adult phenotype.   

In this paper, we provide a guided tour of early developmental events of C. elegans connectome. Such a perspective is lacking in the _C. elegans_ literature, and it should be broadly applicable to the study of developmental dynamics. We will build on the work done in Alicea (2018), where the construction of partial connectomes for multiple time points in embryonic development demonstrates how the connectome emerges from developmental cells. Using information from multiple sources, we are able to build a timeline that spans from the birth of the first neuron to the emergence of the first behaviors (Figure 1). We will also ascribe strategies to individual cells that enable them to form electrical connections. This information processing capacity is the product of cellular identity, which is a combination of relative factors (anatomical position or birth order) and internal factors (molecular properties). While we do not identify causal factors, they might be better understood using simulation approaches included in the discussion section.

### Establishing the Timing of Connectogenetic Events
The nematode _C. elegans_ has been chosen for this study for two reasons. The first is a well-established community of open resources that enable the integration of connectomic, developmental, and molecular data. Secondly, the straightforward mapping between developmental cell lineages, differentiating neurons in the embryo, and the adult phenotype helps us to establish associations between the two stages of life-history. While _C. elegans_ neurodevelopment is deterministic, the connectome is both small and functionally diverse. The adult connectome consists of 302 neurons in the hermaphrodite (White et.al, 1986) and 385 cells in the male (Cook et.al, 2019). We can thus trace the individual components of connectogenesis in a tractable manner. The lack of functional ambiguity in our model organism provides both well-established patterns of connection and well-defined structural features (Varshney et.al, 2011). 

Our characterization of differentiation events of the connectome as predicted from observations of embryo phenotypes. In this paper, we use an informatics approach to associate identified terminally-differentiated neuronal cells with their adult identities. Yet we must recognize that the expression of genes and ion channels are not synonymous with the first appearance of a specific cell. Even though C. elegans has a deterministic developmental trajectory with respect to cell lineage and identity, this process involves the gradual expression and maintenance of transcription factors. The terminal selector (Hobert, 2016a), transcriptional mechanism serves to simultaneously initiate and maintain cell fate choice. Protectors/stabilizers (Zheng and Chalfie, 2016) then ensure the smooth, uninterrupted expression of terminal selectors over time. The notion that neuronal differentiation is a complex process that unfolds over time is most important to understanding connectogenesis. 

<p align="center">
  <img width="480" height="576" src="https://github.com/devoworm/Raising-the-Worm-Brain/blob/master/Figures/Figure-3-timeline.png"><BR>
  <b>Figure 1.</b> Timeline that shows major events in <i>C. elegans</i> embryogenesis from fertilization (0 minutes) to hatch from the egg (800 minutes). Click to enlarge.
</p>

It is imperative that details regarding the so-called neuronal identity of these newly-integrating cells be understood in order to understand connectogenesis while also relating this process to functional and behavioral phenomena (Hobert, 2016b). C. elegans neurons undergo a multipotency-to-commitment transition (MCT), in which neuronal cells are born from a diverse developmental cell lineage that also gives rise to muscle and epithelial cells (Rothman and Jarriault, 2019). This may provide a basis for great electrophysiological diversity across cells in very distinct subcircuits relevant to behavior. As we will see, there is a difference between functional asymmetry and cell lineage asymmetry which is partially driven by the expression and function of ion channels. In addition, while the anatomical distribution of neurons generally remains conserved throughout development (Nicosia et.al, 2013; Alicea, 2017), a number of post 400-minute transformations define connectivity and ultimately organismal-level behaviors. These transformations are often connected to the increasing asymmetry in phenotype as the spherical egg becomes an asymmetrical organism (Gordon and Gordon, 2016).

#### Outline of Approach
This analysis in this paper will involve four basic components. The first of these involves an analysis of cells at different points in time (Alicea et.al, 2018), allowing for an inventory of the various tissue and organ types represented by newly differentiated neurons. Ion channel data collected from WormBase (Harris et.al, 2019) will be used to identify key genes, associated cells, and annotations. Determining the relationships between functional gene identities, specific ion channels, and functional annotations will be enhanced by using data sets (see Methods) developed at the OpenWorm Foundation (Sarma et.al, 2018). This analysis yields information regarding ion channel types present at a specific time point in embryogenesis. 

In terms of the latter, the data set featured in (Packer et.al, 2019) can be used in conjunction with annotation metadata and embryonic gene expression information to draw conclusions regarding the phylogenetic and developmental origins of the connectome. Of particular interest is the link between ion channels expressed by neuronal cells present in the embryo and the lineage-specific expression of ion channel-related and other associated genes. The final component relies upon how stereotypical _C. elegans_ behaviors are heavily influenced by genetics to establish a link between the presence of certain neurons and the potential for early forms of chemosensation, thermosensation, and even learning and memory (Walker et.al, 2019).

### Methods
To make associations between the identity of new neurons and their later molecular identity, an informatics approach is utilized. For each timepoint, the newly terminally-differentiated neurons are defined and matched to information about gene expression and other attributes of selected cells using open data resources from OpenWorm and WormBase. To conduct the first-mover analysis, we use secondary data on synaptogenesis in larval development and couple this with cell lineage timing data from Bhatla (2011) to determine strategies for our model.

#### OpenWorm Resources
Functional annotations are courtesy of Stephen Larson and Mark Watts from datasets provided by the [OpenWorm Foundation](http://openworm.org). The DevoWorm group has also assembled a number of bioinformatic conversions that have been used to track the birth times and developmental lineage of each cell in the _C. elegans_ connectome. These data can be found on [Github](https://github.com/devoworm/DevoWorm) and the Open Science Framework (Alicea, 2018). 

#### WormBase
Supplemental information about protein expression and cells of interest are retrieved from [WormBase Version:WS273](https://www.wormbase.org/). WormBase (Harris et.al, 2019) is a _C. elegans_ community resource that allows us to map between specific cells and the properties of their adult phenotypes. 

#### Data for First-mover Analysis
2,809 potential cell-cell pairwise (_i,j_) relationships denoting pre and postsynaptic relationships are used to determine the first-mover behavior of 58 cells in the adult connectome are taken from Witvliet et.al (2020). The birth time difference measure is calculated as a difference between the birth time of a single presynaptic neuron and the birth time of a single postsynaptic neuron. Negative values represent presynaptic cells that were born first, while positive values represent presynaptic cells that were born second. In calculating times for our strategies, the mean time for all pairwise comparisons for a single row or column in the pairwise matrix _i,j_ are used. These times are further decomposed into positive and negative components, which are then used in calculating the birth time difference. All notes, figures, and code associated with the first-mover model are located in a [Github repository](https://github.com/devoworm/Raising-the-Worm-Brain).

#### Utilities for first-mover model
Employing a series of strategies over time results in a payoff for each cell that is semi-independent of its specific set of preferred strategies. The payoffs determine the costs and benefits of what it means to be a first-mover, a subsequent-mover, or a random mover. Our estimated components of utility can be defined as follows: _FREQ_ represents empirically-observed frequencies in development, _M_ represents an estimate of the molecular milieu), and _N_ represents an estimate of the neurophysiological milieu. This can be estimated in a context-dependent manner, while the formulation is shown for the _C. elegans_ connectome in Table 1.

<p align="center">
Table 1. Payoff matrix for a presynaptic cell that makes a connection with another cell in the nervous system.
</p>
                 | First-mover         | Subsequent-Mover |   Random   |
-----------------|---------------------|------------------|------------|
First-mover      |      -              | FREQ * (M + N)   | FREQ * 0.5 |
Subsequent-Mover |  1 - FREQ * (M + N) |        -         | FREQ / 0.5 |
Random           |     FREQ * 0.5      |    FREQ / 0.5    |      -     |

### Results
The first part of this analysis will proceed by walking through the progression of developmental events in two orthogonal ways. One characterization involves looking at temporal progression. Our inquiry begins before the differentiation of neuronal cells, and the proto-connectome as it exists at five points during embryogenesis (265, 280, 290, 300, and 400 minutes post-fertilization). These networks are defined in Alicea (2018), where the progression of connectogenesis is defined indirectly in terms of cells present. The second characterization involves characterizing molecular properties and events associated with the terminally differentiated neurons. Some of these features (ion channels and gene expression patterns) are not explicitly related to the developmental process, but do allow us to think about the adult connectome as a developmentally contingent structure. Other features, such as the NSY-5 subnetwork, will be analyzed more directly in terms of developmental mechanisms. Such subnetworks are defined by their molecular properties, and have implications for the emergence of large-scale developmental patterns such as functional asymmetry. The second part of the analysis will introduce a first-mover model to understand the sequential behaviors of individual neuronal cell identities that underlie electrical wiring and the establishment of behaviors in the larval and adult worm.

#### Large-scale Morphogenetic Trends
To momentarily step back from issues of terminally-differentiated cell identity, we consider the birth time of the developmental precursors of connectome cells (Sulston et.al, 1983). Considering bursty events that precede the emergence of neuronal cells might provide information about large-scale morphogenetic trends at the organismal level. Figure 2 shows a complex distribution for the birth of developmental cells across the so-called first proliferation phase (Altun and Hall, 2011). While the birth of developmental cells occurs in aperiodic bursts during this interval, there are three bursts of particular interest to our sampling of neuronal cell births. The first burst of births are shown in red, and occur from 210 to 285 minutes. Next is a burst of developmental cell births shown in orange, and occurs from 285 to 345 minutes. While there are no developmental cell births from 345 to 365 minutes, there is a third burst of births from 365-400 minutes of embryogenesis. Based on a prior analysis of the data (Alicea et.al, 2019), bursts of developmental cell births may precede rounds of neurogenesis. The aggregate measure shown in Figure 2 is consistent with the finding that cellular specialization is coordinated with rounds of cell division, although this does not result from a specific cell division-related mechanism (Alberts et.al, 2002). The first few neurons and major expansion in the number of neurons occur immediately after the first two bursts of developmental cell proliferation.

<p align="center">
  <img width="455" height="300" src="https://github.com/devoworm/Raising-the-Worm-Brain/blob/master/Figures/Figure-1.png"><BR>
  <b>Figure 2.</b> Developmental precursors to the first connectome cells to terminally-differentiate in the embryo. Data are arranged as a histogram with bins of size 8. Red, Orange, and Gray bars are bins of particular interest to our sampling scheme. Click to enlarge.
</p>

__Connectogenesis from 265 to 400 minutes post-fertilization.__ At 265 minutes, we have one asymmetric cell that emerges: RMEV. RMEV is a ring motor neuron, and does not have a bilateral partner. According to Gendrel et.al (2016), RMEV forms part of the GABAergic nervous system in C. elegans, which constitutes nearly half of the adult C. elegans connectome. While RMEV serves as a founder cell (first cell to emerge in connectogenesis) for this network, its functional role as a core node in this subnetwork is not clear.

For the 280 minute connectome, there are five terminally-differentiated neurons: RMEV (born at 265 minutes), and two symmetric pairs of neurons (ADFL/R and AWBL/R). ADFL and ADFR have been identified as chemosensory sheath cells that detect volatile compounds (Bargmann, 2006). Looking back at Figure 1, this represents the emergence of components in a functional circuit well before there are any environmental or activity-dependent signals to shape their fate. As harbingers of neuronal function, AWBL and AWBL are also important for their role in the NSY-5 network. NSY-5, a protein resulting from expression of the inx-19 gene, forms a gap junction network during embryogenesis with 32 other cells in the nervous system (Chuang et.al, 2007). About half of these cells share the same lineage, and the NSY-5 network as a whole is required for stochastic, asymmetric gene expression (Alqadah et.al, 2016).  

The 290 minute connectome expands to 38 terminally-differentiated neurons distributed outside of what will become the head for the first time (see Figure 3). There are a number of neuronal pairs born at this time, as well as several asymmetric terminal-differentiation events. We can focus on two groups (AV and IL2) to appreciate the beginnings of functional architecture established at this point in development. Just considering AV neurons born at 290 minutes of development (AVDL, AVDR, AVJL, AVJR, AVKL, AVKR, AVL), WormBase confirms that these cells play a crucial role in the mechanosensory function of the adult worm. 

IL2 neurons (IL2DL, IL2DR, IL2L, IL2R, IL2VL, IL2VR) begin to form the inner labial structure of the head at this time, and play a functional role in larval plasticity. IL2 plasticity is crucial for enhanced sensory capabilities during Dauer formation (Procko et.al, 2011; Androwski et.al, 2017). IL2 also expresses behaviorally-relevant proteins such as OSM-9 and EGL-2. The former protein (OSM-9) has been implicated in a feeding behavior called osmotic avoidance (Hallam and Sternberg, 2008). IL2 neurons originate from the ABal and ABar sublineages (Wu et.al, 2011). In terms of connectogenetic function, IL2 has been implicated in nictation and dispersal behaviors during the Dauer stage (Albert and Riddle, 1983). 

One cell pair that emerges at 300 minutes post-fertilization is AWCL/R. These are the Amphid Wing C neurons that will be essential post-hatch development for olfaction and form the basis for the NSY-5 subnetwork. In adulthood, AWCL/R neurons are unique among C. elegans olfactory receptors as they exhibit a fluctuation of intracellular calcium ions consistent with odorant stimulation, particularly the presentation and removal of the stimulus (Chalasani et.al, 2007). A computational model has demonstrated that the AWC cell pair are susceptible to noise, even when ion channels that mediate Ca2+ influx were included (Usuyama et.al, 2012).

In terms of laying the foundation for a functional circuit, AWCL/R olfactory neurons work cooperatively with AIBL/R and AIYL/R interneurons to form an adaptive unit that responds to food and odorants (Chalasani et.al, 2007). In both larvae (post-hatch development) and adults, the presentation of an olfactory stimulus can act to override this inhibition of AIYL/R cells. From our terminal differentiation temporal data, we can see that while AIBL/R and AWCL/R are born at 300 minutes, the AIYL/R interneuron does not appear until our 400 minutes sampling time. Whether these functional differences are influenced by these differences in birth times is not known.

<p align="center">
  <img width="334" height="277" src="https://github.com/devoworm/Raising-the-Worm-Brain/blob/master/Figures/Figure-2.png"><BR>
  <b>Figure 3.</b> Distribution of cell types (based on families in Alicea et.al, 2019) born at 290 minutes. Click to enlarge.
</p>
  
A total of 87 new neurons differentiate between the 300 and 400 minute sampling intervals. Table 2 shows (by cell family) all new cells that occur in the 400 minute sampling interval that are not present in the 300 minutes sampling interval. The most abundant newly-differentiated neuronal families include members of the AV family (14 cells), RI family (9 cells), RM family (7 cells), and UR family (6 cells). Our 400 minute sampling interval also reveals the diversity of timing among inner labial (IL) neurons. For example, IL2 neurons are born at 290 minutes, whereas IL1 neurons appear at 400 minutes of embryogenesis. Despite this, each pair of neurons are cholinergic polymodal neurons (Pereira et.al, 2015) that have multiple mechanosensory functions in the adult (Goodman, 2006). While WormBase confirms that IL1 neurons enable mechanosensation in the adult worm, mechanosensation itself only becomes important later in development (post-hatch). As mentioned during the 280 minute analysis, we see neurons that form a functional circuit emerge well before the associated behaviors themselves. 

<p align="center">
Table 2. Terminally-differentiated neurons present at 400 minutes of development versus 300 minutes of development. Cell family classifications are used, and a distribution across cell families is provided.
</p>
Cell  | Family	Number |
------|----------------|
  AF  |     	2        |
  AI  |     	6        |
  AL  |     	1        |
  AS  |     	10       |
  AU  |      	2        |   
  AV	|       14       |
  AW  |     	2        |
 CEP  |     	3        |
  DV  |     	3        |
 IL1  |     	4        |
 IL2  |     	1        |
  LU	|       2        |
 OLQ  |     	2        |
  PD  |	      1        |
  PH	|       2        |
  PV  |     	5        |
  RI  |     	9        |
  RM	|       7        |
  SI  |     	1        |
  SM  |	      4        |
  UR  |     	6        |
 
__Connectogenesis post-400 minutes.__ There are a number of organismal level developmental events that occur after the 400-minute mark that are relevant to neuronal function. The 400 minute mark defines the beginning of the comma stage of development, where the head becomes thicker than the body and elongates correspondingly (Christensen et.al, 2015). Approximately 450 minutes post-fertilization (see Figure 3) marks the first evidence of axonal outgrowth (Morck et.al, 2003; Taylor et.al, 2010). From this time until hatching of the egg (800 minutes; Sulston et.al, 1983), we observe the onset of asymmetric gene expression in symmetric pairs of neurons. This is exemplified in neurons constituting the NSY-5 network (Hobert et.al, 2002; Taylor et.al, 2010). There is also an increasing asymmetry of phenotype outside of the connectome, as the hypodermis, muscle syncytium, and intestines all begin to take shape. This period between the embryonic neuronal birth and the onset of connectome-related behavior is an interesting period of time which will be discussed later in the paper.

__Timing of NSY-5 subnetwork.__ Due to a number of functional attributes, the innexin-dependent NSY-5 network is worth examining in more detail. There are 28 left/right pairs of cells in this network: ADA, ADF, ADL, AFD, AIM, AIZ, ASH, ASI, ASK, AWB, AWC, BAG, and RIC. The NSY-5 network exhibits stochastic differentiation (Johnston and Desplan, 2008), which decouples the identity of developmental lineages from the transcriptional activity of terminally-differentiated cells (Packer et.al, 2019). As opposed to our time-threshold networks, neurons included in this network are defined by their expression of NSY-5 (Chuang et.al, 2007). The first neurons in this network appear at 280 minutes, and continue to appear until after 400 minutes post-fertilization. At least one set of neurons in this network (AWCL/R, or Amphid Wing C cells) are influenced by calcium influx through voltage-gated calcium channels (Hseih et.al 2014). In particular, the NSY-5 network is required for left/right gene expression asymmetry in AWC neurons. 

Overall, this network consists mainly of cells associated with Amphid Sheath and Neuropil, or function as Interneurons and Sensory Neurons. While the left-right asymmetry of cell differentiation is somewhat uncommon (about 1/3rd of all terminally-differentiatied cells) in C. elegans, functional asymmetry for properties such as gene expression is much more common (Hobert et.al, 2002). Among AWC neurons, functional asymmetry is much more common than birth asymmetry, which is greater than 50 minutes in only two pairs of NSY-5 cells (ASHL/R and PVQL/R). By comparison, symmetric induction of NSY-5 in AWC neurons occurs 150 minutes after their birth time, which is well after birth time but still falls within pre-hatch development (Taylor et.al, 2010). 

__Critical neurons and their cholinergic expression.__ To conclude with this survey, we will turn to the intersection of network functionality and the role of cholinergic neurons. Through a series of computational experiments, Kim et.al (2016) have identified 12 neurons that are critical for connectome function and involve 29 critical synapses. Critical neurons are highly connected compared with other neurons in the same network, and serve to bridge between different modules and reduce the overall number of connections across the connectome. Such neurons are central to a connectome and must be present in order for the various subnetworks of an adult connectome to remain functional. In the face of environmental challenges and mutation, these cells enable the connectome to remain resilient (Gao et.al, 2016) without evolving new innovations. Nine of these 12 critical neurons are born in the hermaphrodite connectome prior to the initiation of the twitching phase (470 minutes). Six of these nine cells have cholinergic function: AVAL/R, PVCL/R, PVPR, and AVER. All of these cells are positive for unc-17/cha-1 and cho-1 expression (Pereira et.al, 2015). These cells also express C. elegans homologues of ACE genes (Schaefer, 2005), which are associated with a host of diverse functions. 
Towlson et.al (2015) have identified a core set of rich club neurons, which also serve as critical for connectome function. This set of 11 cells differs slightly from the Kim et.al (2016) list, and also includes cholinergic neurons AVBL/R, AVDL/R, and AVEL. The map of Pereira et.al (2015) shows that not only are these cells ventral cord interneurons with cholinergic function, they also receive ACh inputs from other cells. It is not clear whether there are additional molecular and/or electrophysiological properties that differentiate rich club neurons from other neurons in the connectome in an a priori manner, but hierarchical relationships with other neurons in the connectome can be approximated using a first-mover model. 

#### First-mover Model of Developmental Dynamics
A first-mover model of developmental emergence will now be introduced to tie together many of these developmental processes. This has parallels with the game-theoretic model of Khajezade et.al (2019), in which utility functions derived from a directed Havel-Hakimi network are used to model optimal connectivity in the frontal network of C. elegans connectome. However, their model did not assume that development is a generative process. Our results propose a developmental-specific competitive mechanism (first-mover competition), a formal analysis of observed data (establishment of synaptogenesis), and generalizing the results to a systems-level context.

__First-mover Competitive Interactions.__ The first-mover model describes neurons that are born and eventually connect to an expanding network. As a sequential process, pairs of neurons engage in a leader-follower dynamic to establish connections. In this type of competition, there are first movers (leaders), who establish the nature of the dyadic relationship, as well as second movers (followers), who are constrained by the outcome of the first move. In this instance, a single move is a connection between two cells, initiated by the first mover. In a sequential interaction, initial two-player competitions and their associated outcomes provide information but also increasingly limited options for later competitions. This might lead to suboptimal outcomes or the selection of multiple strategies for a single cell identity. 

Each neuron has a suite of available strategies. Such profiles are heterogeneous, and can influence the gene expression of newly-connected cells based on the principle of first-mover. The goal of a first mover advantage and the shifting dynamics that new agents with heterogeneous strategies provides a means to achieve leader-follower behavior that imposes order upon a developmental system. The first-mover model provides us with a hypothetical model for the structure of developmental wiring. One such strategy is the fitness-based connectivity criterion of Bianconi and Barabasi (2001). Given a selection scheme such as rank or tournament selection (Hamblin, 2012), neurons will connect at different rates to its neighbors based on some functional objective. 

__First-mover analysis with synaptogenesis data.__ Using a dataset from Witvliet et.al (2020), we have extracted strategies from cell pairings (see Methods). These pairwise comparisons of neuronal cells in terms of pre and postsynaptic relationships suggests that first-mover connection behaviors are general tendencies. In Figure 4, we integrate the synaptic formation data with birth time data for each cell. A simple comparison of the difference in birth time yields a fairly regular distribution of points around zero difference, suggesting that individual events are not informative of strategies employed by cells given a wider range of contexts. Interestingly, the distribution for developmentally-specific and stable synaptic relationships are skewed slightly to presynaptic cells being born later than postsynaptic cells. 

To make these data relevant to formal strategies, we make two assumptions about how connection behaviors exhibited by cells can be viewed as decision-making. First, cells make their decision about which strategy to employ not based on individual contacts, but on a memory of prior states. To reveal this, a raw averaging of birth time difference is not informative due to the great variety and sometimes trivial difference in birth times between cells.

__Observed strategies.__ We will now walk through the various strategies cells employ during synaptogenesis, in addition to the consequences of these strategies. First-mover dynamics are based on scenarios where all players (in this case cells) have imperfect information. There are two types of strategy: pure and mixed. Pure strategies are those that do not overlap with other strategies, while mixed strategies are those that overlap with other strategies. The consequences and broader implications of each strategy are shown in Figure 5, while the prevalence and outcomes of all strategies extracted from the data are shown in Table 3. By separating the developmental birth time data into positive and negative components for both presynaptic and postsynaptic partners, we have identified five strategies.

<p align="center">
  <img width="400" height="400" src="https://github.com/devoworm/Raising-the-Worm-Brain/blob/master/Figures/Figure%204A.png"><BR>
  <b>Figure 4.</b> Distribution of synaptic relationships (for three different functional states) in terms of the difference in birth time between pre and postsynaptic cells. Negative values represent relationships where the presynaptic cell is born first in embryogenesis, while positive values represent relationships where presynaptic cells are born after the postsynaptic partner. Click to enlarge.
</p>






















<p align="center">
  <img width="480" height="270" src="https://github.com/devoworm/Raising-the-Worm-Brain/blob/master/Figures/Figure%205A.png"><BR>
  <img width="480" height="270" src="https://github.com/devoworm/Raising-the-Worm-Brain/blob/master/Figures/Figure%205B.png"><BR>
  <img width="480" height="270" src="https://github.com/devoworm/Raising-the-Worm-Brain/blob/master/Figures/Figure%205C.png"><BR>
  <b>Figure 5.</b> Schematic of first-mover dynamics. A: a simple relationship between endogenous processes and inputs, B: a potential first-mover strategy for intrinsic circuits (time of birth in hypothetical minutes), C: transformation from circles (that constitute networks) to boxes. Click to enlarge.
</p>
  
In a sequential game, initial moves and their associated payoffs provide context for endogenous behavior in newly-connected cells. This allows neurons to be reorganized in terms of function rather than anatomical structure. Over time, as newer cells are integrated into the network, subsequent moves further constrain the function of the intrinsic circuit until all cells are connected. However, new inputs from older cells can disrupt this first-mover advantage by re-establishing the role of each cell in the new circuit.
Neurons are defined as agents, and each agent has a suite of strategies which are either determined by an interaction rule or their K+ ion channel profile (as shown in Figure 5A). Such profiles are heterogeneous, and can influence the gene expression of newly-connected cells based on the principle of first-mover. The goal of a first mover advantage and the shifting dynamics that new agents with heterogeneous strategies provides is to achieve leader-follower behavior that imposes order upon a developmental system.

The first-mover model provides us with a hypothetical model for the structure of developmental wiring. To infer the function of wiring, we can apply a mapping between the first-mover game and a neuroethological diagram. This is a circle to boxes transformation, which takes a subset of cells with functional significance and defines them as a box. This transformation reassembles the anatomical structure lost in the wiring step, and provides a mapping between the organization of the connectome and the execution of behavior.

In Figure 5B, we assumed one possible strategy for connecting neurons electrically (neural fate seniority with preferential attachment). In cases where there is no lineage tree with programmed fates, there are other potential strategies that allow us to explore the role of the changing electrophysiological milieu in developing neurons. One such strategy is the fitness-based connectivity criterion of Bianconi and Barabasi (2001). In this instance, each neuron might be modeled with a preference for a specific set of K+ channels. Given a selection scheme such as rank or tournament selection (Hamblin, 2012), neurons will connect at different rates to its neighbors based on some functional objective. 

### Discussion
This paper presents several key findings that flesh out aspects of the developmental connectome. We provide a guided tour of early developmental events related to newly-differentiated neurons and their physiological context. In addition, we systematically walk through the developmental connectome at different periods of embryogenesis and attach information regarding the expression of ion channels. We also demonstrate the timing, identity, and properties of ion channel-relevant subnetworks. 

#### Limitations of Approach
There are several limitations of this approach. The first limitation is the use of informatics as an inferential tool. While we have been able to integrate multiple sources of data, direct observations of the system itself are as of yet not available. Yet despite these limitations, we can provide a significant view of an emerging nervous system. This can be done in _C. elegans_ for two reasons: a deterministic cell lineage (Sulston et.al, 1983) and eutelic adult phenotype (Sulston and Horvitz, 1977). Even in cases where there is variability in the developmental process across individuals, we should expect this variability to be predictable (Azevedo and Leroi, 2001). 

#### Broader Implications
There are several broader implications to this work. The first is to flesh out a model of explicit steps in relation to the development process and with respect to an emerging connectome. The second involves informing developmental models of nervous system function. Mapping ion channel and electrical function onto connectome architectures is useful for modeling function during the formation of the connectome. This provides a basis for understanding the emergence of specific behaviors and behavioral circuits. 

As the _C. elegans_ connectome is considered analytically tractable, we hope that the extraction and analysis of neuronal populations at different points in embryonic development can be applied to other small connectomes (<1000 neurons). The polycheate (Windoffer & Westheide, 1988; Hochberg, 2009) and the larval tunicate _Ciona intestinalis_ (Bezares-Calderon & Jekely, 2016; Ryan et.al, 2016) are two such examples. The tunicate model is especially interesting, as it provides an opportunity to study asymmetry. Yet we also see how the emergence of behaviors are context-specific, as swimming in _C. intestinalis_ (Zegal et.al, 2006) emerges in a way that is fundamentally different from behaviors such as pharyngeal pumping in _C. elegans_.

#### Development and Neuronal Criticality
Considering neuronal criticality more broadly, Towlson et.al (2013) have defined rich club neurons in the adult phenotype as highly-connected neurons and serving a special functional role due to their ability to connect different modules. One question for future research is whether or not the rich club originates from the rules of preferential attachment (Barabasi & Albert, 1999), or if their functional attributes make them prone to being highly-connected. As they tend to be born between 290 and 350 minutes of development (Alicea, 2019), birth order is not the preferential criterion for this functional role. In any case, we can observe the signature of a small-world network (Watts & Strogatz, 1998) in both the _C. elegans_ and _C. intestinalis_ larval connectomes (Bezares-Calderon & Jekely, 2016). This suggests whatever interactions are determining critical structure is common across developing small connectomes.

#### From Embryogenesis to Behavior
Our ability to infer behavioral pathways as they form in embryogenesis can yield information about how and why behavioral circuits form in development. To see the value of this information, we can recall Tinbergen’s four questions with respect to an organismal trait: what is its structure, what is its function, how did it get there in development, and how did it get there in evolution (Bateson and Laland, 2013). In this paper, we address three of these (structure, function, and development). Based on this analysis of _C. elegans_ data, an order of origins can be proposed: developmental processes (cellular differentiation) generate structure (the birth of circuit components), which in turn leads to function (electrical connections between neurons and the generation of behaviors). To further support this hypothesis, structures such as muscle autonomously generate behaviors prior to innervation by axonal connections. We will now review such behavioral transitions to demonstrate how structure comes before function.
  
The first visible motor activity in the embryo is twitching (see Figure 2), which begins at 470 minutes of development (Kim et.al, 2016). Twitching is defined by spreading calcium waves in muscles and calcium transients in motor circuit neurons (Ardiel et.al, 2017). While the earliest twitches are purely myogenic in origin, later twitches (once synaptic connections are established) are controlled by the cells in what will be the adult motor circuit (Ardiel et.al, 2017). One of the first complex behaviors exhibited by _C. elegans_ is pharyngeal pumping (see Figure 2). Pilon and Morck (2005) make two observations about the origins of the pharynx. One is that the morphological components of the functional pharynx (organ shape and position) become established between 430 and 760 minutes of development (Portereiko & Mango, 2001). The other is that rhythmic contractions of the pharynx can occur in the absence of neuronal control (Avery & Horvitz, 1989). Efficient pharyngeal pumping (which does require neuronal control) is vital to life outside of the egg, and thus occurs at around 760-780 minutes of development (Chisholm and Hardin, 2005). This type of structure-function relationship is observed in other small connectomes as well. In _C. intestinalis_ larvae, both tail flicks and phototropisms are generated by muscles before there are connections with neurons (Bezares-Calderon & Jekely, 2016). 

#### Implications of First-mover Model
There are a number of potential uses for first-mover models to bridge function and behavior. Clement (1987) suggests that a solid mapping between neurotransmitters, sensory devices, muscles, and organ systems allows us gain knowledge with respect to function. Our combination of game theory with neuroethological diagrams provides a means for establishing this mapping, which help to clarify some limitations of the informatics approach. While direct observation of the connectome is sparse, first-mover models allow us to postulate potential mechanisms for initiating the self-organization of developmental complexity.

This leads us to a question: do we understand the process of “booting up” a connectome? Using physical connectivity information (gap junctions) in tandem with time-series sampling, we observe a number of steps to the construction of a connectome. At 280 minutes for example, we observe both what will become reciprocally connected pairs of cells (ADFL/R and AWBL/R) and a disconnected cell (RMEV) whose network partners have yet to be born. Observations such as these resemble what Betzel et.al (2016) term a generative connectome. As the adult connectome exhibits a hierarchical structure where some neurons are more central to the network (demonstrated in terms of more dense connectivity) than other cells, we must also ask how this comes to be. It has previously been found that early-born neurons tend to be both more highly connected and exhibit more longer-range connections than later-born neurons (Varier and Kaiser, 2011). Yet neuronal birth time is not particularly informative of the details of later synaptic connectivity (Kratsios et.al, 2015). In this paper, we propose that criteria such as preferential attachment or fitness might play a role in shaping the adult nervous system’s connectivity patterns. In turn, a first-mover model allows us to characterize these different hypotheses, in addition to synthesizing what is known with respect to the molecular and electrophysiological properties of connecting cells.
  
#### Towards Brain Simulations
Another area in which this study would be of value is in informing simulations studies. One example from _C. elegans_ involves the c302 project (Gleeson et.al, 2018), which is an attempt to simulate various aspects of the adult nervous system. Such a model adapted for embryonic and larval development would help to close the empirical gaps of the current approach. Of particular interest is the platform’s ability to simulate subcircuits and how this might be used to recapitulate the developmental process. Applying c302 to a developmental context might mean simulating early-stage ion channel expression (Rutenberg et.al, 2002) and the activity of ion channels in the absence of electrical connections. This might be done by hypothesizing which ion channel become functional when among the cells switched on at different times. Yet even with the work of OpenWorm, we still need two pieces of information on the underpinnings of behavior: a functional connectivity map at the biochemical level, and a systems-level map of experience-dependent plasticity (based on Schaefer, 2005).

The advancement of work on Developmental Braitenberg Vehicles (BVs - Braitenberg, 1984) might also allow us to evaluate the emergence of cells and activity patterns in the context of embodied development (Dvoretskii et.al, 2020). This takes the first-mover model a step further to provide both environmental and sensorimotor feedback, which play a role in bridging the gap between self-generated twitching and coherent sensorimotor behaviors (Narayanan & Ghazanfar, 2014). While Developmental BVs provide a connectionist view of an emerging connectome, these connections can be modulated by mechanisms that are activated or fluctuate during the process of interacting with its environment. Developmental BVs also rely on systems-level regulatory mechanisms such as fitness functions or Hebbian learning mechanisms. A similar type of mechanism is likely to be critical for developing biological connectomes as well. Brought into the context of electrophysiological function, we can look toward multilevel Developmental BVs that model gene expression using artificial Genetic Regulatory Network (GRN) models (Cussat-Blanc et.al, 2019) as a means to augment the function of a connectionist network.

### References
Albert, P.S. & Riddle, D.L. (1983). Developmental alterations in sensory neuroanatomy of the _Caenorhabditis elegans_ dauer larva. _Journal of Comparative Neurology_, 219(4), 461-481. doi:10.1002/cne.902190407.

Alberts, B., Johnson, A., Lewis, J., Raff, M., Roberts, K., & Walter, P. (2002). _Caenorhabditis Elegans_: development from the perspective of the individual cell. In "Molecular Biology of the Cell", 4th edition. Garland Science, New York. https://www.ncbi.nlm.nih.gov/books/NBK26861/

Alicea, B., Gordon, R., & Portegys, T.E. (2019). Data-theoretical Synthesis of the Early Developmental Process. _bioRxiv_, doi:10.1101/282004.

Alicea, B., Gordon, R., & Banerjee, A. (2018). Dataset: Embryo networks and connectomes in _Caenorhabditis elegans_. doi:10.17605/OSF.IO/Q9JVB. https://osf.io/q9jvb/

Alicea, B. (2017). The emergent connectome in _Caenorhabditis elegans_ embryogenesis. _BioSystems_, 173, 247-255.

Alqadah, A., Hsieh, Y.W., Xiong, R., & Chuang, C.F. (2016). Stochastic left-right neuronal asymmetry in _Caenorhabditis elegans_. _Philosophical Transactions of the Royal Society of London B_, 371(1710), 20150407.

Androwski, R.J., Flatt, K.M., & Schroeder, N.E. (2017). Phenotypic plasticity and remodeling in the stress-induced _C. elegans_ dauer. _Wiley Interdisciplinary Reviews: Developmental Biology_, 6(5). doi:10.1002/wdev.278.

Ardiel, E.L., Kumar, A., Marbach, J., Christensen, R., Gupta, R., Duncan, W., Daniels, J.S., Stuurman, N., Colon-Ramos, D., & Shroff, H. (2017). Visualizing calcium flux in freely moving nematode embryos. _Biophysical Journal_, 112, 1975–1983.

Avery L. (1993). Motor neuron M3 controls pharyngeal muscle relaxation timing in _Caenorhabditis elegans_. _Journal of Experimental Biology_, 175, 283-297.

Avery, L., & Horvitz, H.R. (1989). Pharyngeal pumping continues after laser killing of the pharyngeal nervous system of _C. elegans_. _Neuron_, 3, 473–485.

Azevedo, R.B.R. & Leroi, A.M. (2001). A power law for cells. _PNAS_, 98(10), 5699–5704.

Barabasi, D.L. & Barabasi, A-L. (2020). A Genetic Model of the Connectome. _Neuron_, 105, 1–11.

Barabasi, A-L. & Albert, R. (1999). Emergence of scaling in random networks. _Science_, 286(5439), 509–512.

Bargmann, C.I. (2006). Chemosensation in C. elegans, WormBook. The _C. elegans_ Research Community (eds). _WormBook_, doi/10.1895/wormbook.1.123.1. 

Bateson, P. & Laland, K.N. (2013). Tinbergen’s four questions: an appreciation and an update. _Trends in Ecology and Evolution_, 28(12), 712-718.

Berck, M.E., Khandelwal, A., Claus, L., Hernandez-Nunez, L., Si, G., Tabone, C.J., Li, F., Truman, J.W., Fetter, R.D., Louis, M., Samuel, A.D., & Cardona, A. (2016). The wiring diagram of a glomerular olfactory system. _eLife_, 13, 5.

Betzel, R.F., Avena-Koenigsberger, A., Goni, J., He, Y., de Reus, M.A., Griffa, A., Vertes, P.E., Misic, B., Thiran, J-P., Hagmann, P., van den Heuvel, M., Zuo, X-N., Bullmore, E.T., & Sporns, O. (2016). Generative models of the human connectome. _Neuroimage_, 124(A), 1054–1064.

Bezares-Calderon, L.A. & Jekely, G. (2016). Think small. _eLife_, 5, e22497. doi:10.7554/eLife.22497.

Bhattacharya, A., Aghayeva, U., Berghoff, E.G., & Hobert, O. (2019). Plasticity of the electrical connectome of _C. elegans_. _Cell_, 176(5), 1174-1189. doi:10.1016/j.cell.2018.12.024. 

Bianconi, G., Barabasi, A.L. (2001). Competition and multiscaling in evolving networks. _Europhysics Letters_, 54(4), 436–442.

Bozorgmehr, T., Ardiel, E.V., McEwan, A.H., & Rankin, C.H. (2013). Mechanisms of plasticity in a _Caenorhabditis elegans_ mechanosensory circuit. _Frontiers in Physiology_, 4, 88.

Braitenburg, V. (1984). Vehicles: experiments in synthetic Psychology. MIT Press, Cambridge, MA.

Cao, M., Huang, H., Peng, Y., Dong, Q., & He, Y. (2016). Toward Developmental Connectomics of the Human Brain. _Frontiers in Neuroanatomy_, 10, 25. doi:10.3389/fnana.2016.00025.

Chalasani, S.H., Chronis, N., Tsunozaki, M., Gray, J.M., Ramot, D., Goodman, M.B., & Bargmann, C.I. (2007). Dissecting a circuit for olfactory behaviour in _Caenorhabditis elegans_. _Nature_, 450(7166), 63-70.

Chisholm, A.D. & Hardin, J. (2005). Epidermal morphogenesis. WormBook, ed. The _C. elegans_ Research Community. _WormBook_, doi:10.1895/wormbook.1.35.1.

Christensen, R.P., Bokinsky, A., Santella, A., Wu, Y., Marquina-Solis, J., Guo, M., Kovacevic, I., Kumar, A., Winter, P.W., Tashakkori, N., McCreedy, E., Liu, H., McAuliffe, M., Mohler, W., Colon-Ramos, D.A., Bao, Z., & Shroff, H. (2015). Untwisting the _Caenorhabditis elegans_ embryo. _eLife_, 4, e10070 doi:10.7554/eLife.10070.

Chuang, C.F., Vanhoven, M.K., Fetter, R.D., Verselis, V.K., & Bargmann, C.I. (2007). An innexin-dependent cell network establishes left-right neuronal asymmetry in _C. elegans_. _Cell_, 129(14), 787-789.

Clement, P. (1987). Movements in rotifers: correlations of ultra-structure and behavior. _Hydrobiologia_, 14, 339–359.

Cook, S.J., Jarrell, T.A., Brittin, C.A., Wang, Y., Bloniarz, A.E., Yakovlev, M.A., Nguyen, K.C.Q., Tang, L.T-H., Bayer, E.A., Duerr, J.S., Bulow, H.E., Hobert, O., Hall, D.H., & Emmons, S.W. (2019). Whole-animal connectomes of both _Caenorhabditis elegans_ sexes. _Nature_, 571(7763), 63-71, doi:10.1038/s41586-019-1352-7.

Cussat-Blanc, S., Harrington, K., & Banzhaf, W. (2019). Artificial Gene Regulatory Networks: a review. _Artificial Life_, 24(4), 296-328.

Dent, J.A. (1997). _avr-15_ encodes a chloride channel subunit that mediates inhibitory glutamatergic neurotransmission and ivermectin sensitivity in Caenorhabditis elegans. _EMBO Journal_, 16(19), 5867–5879.

Dvoretskii, S., Gong, Z., Gupta, A., Parent, J., & Alicea, B. (2020). Braitenberg Vehicles as developmental neurosimulation. _In Progress_.

Eichler, K., Li, F., Litwin-Kumar, A., Park, Y., Andrade, I., Schneider-Mizell, C.M., Saumweber, T., Huser, A., Eschbach, C., Gerber, B., Fetter, R.D., Truman, J.W., Priebe, C.E., Abbott, L.F., Thum, A.S., Zlatic, M., & Cardona, A. (2017). The complete connectome of a learning and memory centre in an insect brain. _Nature_, 548(7666), 175-182.

Faumont, S., Boulin, T., Hobert, O., & Lockery, S.R. (2006). Developmental regulation of whole cell capacitance and membrane current in identified interneurons in _C. elegans_. _Journal of Neurophysiology_, 95(6), 3665-3373. 

Fox, R.M., Von Stetina, S.E., Barlow, S.J., Shaffer, C., Olszewski, K.L., Moore, J.H., Dupuy, D., Vidal, M., & Miller, D.M. (2005). A gene expression fingerprint of _C. elegans_ embryonic motor neurons. _BMC Genomics_, 6, 42.

Gao, J., Barzel, B., & Barabasi, A-L. (2016). Universal resilience patterns in complex networks. _Nature_, 530, 307-312.

Gendrel, M., Atlas, E.G., & Hobert, O. (2016). A cellular and regulatory map of the GABAergic nervous system of _C. elegans_. _eLife_ 5, e17686.

Gleeson, P., Lung, D., Grosu, R., Hasani, R., & Larson, S.D. (2018). c302: a multiscale framework for modelling the nervous system of _Caenorhabditis elegans_. _Philosophical Transactions of the Royal Society B_, 373, 20170379.

Goodman, M.B. (2006). Mechanosensation, WormBook. The _C. elegans_ Research Community (eds). _WormBook_, doi/10.1895/wormbook.1.62.1.

Hallem, E.A. & Sternberg, P.W. (2008). Acute carbon dioxide avoidance in _Caenorhabditis elegans_. _PNAS_, 105(23), 8038-8043.

Hamblin, S. (2012). On the practical usage of genetic algorithms in ecology and evolution. _Methods in Ecology and Evolution_, doi:10.1111/2041-210X.12000.

Harris, T.W. Arnaboldi, V., Cain, S., Chan, J., Chen, W.J., Cho, J., Davis, P., Gao, S., Grove, C., Kishore, R., Lee, R.Y.N., Muller, H-M., Nakamura, C., Nuin, P., Paulini, M., Raciti, D., Rodgers, F., Russell, M., Schindelman, G., Van Auken, K., Wang, Q., Williams, G., Wright, A., Yook, K., Howe, K., Schedl, T., Stein, L., & Sternberg, P.W. (2019). WormBase: a modern model organism information resource. _Nucleic Acids Research_, gkz920, doi:10.1093/nar/gkz920.

Hobert, O., Glenwinkel, L., & White, J. (2016). Revisiting Neuronal Cell Type Classification in _Caenorhabditis elegans_. _Current Biology_, 26(22), R1197-R1203. 

Hobert O. (2016a). Terminal Selectors of Neuronal Identity. _Current Topics in Developmental Biology_, 116, 455-475. doi: 10.1016/bs.ctdb.2015.12.007. 

Hobert, O. (2016b). A map of terminal regulators of neuronal identity in _Caenorhabditis elegans_. _Wiley Interdisciplinary Reviews in Developmental Biology_, 5(4), 474–498.

Hobert, O. (2013). The neuronal genome of _Caenorhabditis elegans_. _WormBook_, August 13, 1-106. doi: 10.1895/wormbook.1.161.1.

Hobert, O., Johnston, R.J., & Chang, S. (2002). Left–right asymmetry in the nervous system: the _Caenorhabditis elegans_ model. _Nature Reviews Neuroscience_, 3, 629–640.

Hoyle, G. (1984). The scope of neuroethology. _Behavioral and Brain Sciences_, 7, 367-412.

Hsieh, Y.W., Alqadah, A., & Chuang, C.F. (2014). Asymmetric neural development in the _Caenorhabditis elegans_ olfactory system. _Genesis_, 52(6), 544-554. doi:10.1002/dvg.22744.

Jin, Y. & Qi, Y.B. (2018). Building stereotypic connectivity: mechanistic insights into structural plasticity from _C. elegans_. _Current Opinion in Neurobiology_, 48, 97–105.

Jorgensen, E.M. & Mango, S.E. (2002). The art and design of genetic screens: _Caenorhabditis elegans_. _Nature Reviews Genetics_, 3(5), 356-369.

Kaiser, M. (2017). Mechanisms of connectome development. _Trends in Cognitive Science_, 21(9), 703-717.

Kim, S., Kim, H., Kralik, J.D., & Jeong, J. (2016). Vulnerability-Based Critical Neurons, Synapses, and Pathways in the _Caenorhabditis elegans_ Connectome. _PLoS Computational Biology_, 12(8), e1005084. doi:10.1371/journal.pcbi.1005084. 

Ko, H., Cossell, L., Baragli, C., Antolik, J., Clopath, C., Hofer, S.B., & Mrsic-Flogel, T.D. (2013). The emergence of functional microcircuits in visual cortex. _Nature_, 496(7443), 96–100.

Kratsios, P., Pinan-Lucarre, B., Kerk, S-Y., Weinreb, A., Bessereau, J-L., & Hobert, O. (2015). Transcriptional coordination of synaptogenesis and neurotransmitter signaling. _Current Biology_, 25(10), 1282–1295.

Mellem, J.E., Brockie, P.J., Madsen, D.M., and Maricq, A.V. (2008). Action Potentials Contribute to Neuronal Signaling in _C. elegans_. _Nature Neuroscience_, 11(8), 865–867. doi:10.1038/nn.2131.

McInnes, L., Healy, J., & Melville, J. (2018). UMAP: Uniform Manifold Approximation and Projection for Dimension Reduction. _arXiv_, 1802.03426.

Morck, C., Axang, C., & Pilona, M. (2003). A genetic analysis of axon guidance in the _C. elegans_ pharynx. _Developmental Biology_, 260(1), 158-175.

Narayanan, D.Z. & Ghazanfar, A.A. (2014). Developmental Neuroscience: how twitches make sense. _Current Biology_, 24(19), R971-R972.

Nicosia, V., Vertes, P.E., Schafer, W.R., Latora, V., and Bullmore, E.T. (2013). Phase transition in the economically modeled growth of a cellular nervous system. _PNAS_, 110(19), 7880–7885. doi:10.1073/pnas.1300753110.

Oren-Suissa, M., Bayer, E.A., & Hobert, O. (2016). Sex-specific pruning of neuronal synapses in _Caenorhabditis elegans_. _Nature_, 533, 206–211.

Packer, J.S., Zhu, Q., Huynh, C., Sivaramakrishnan, P., Preston, E., Dueck, H., Stefanik, D., Tan, K., Trapnell, C., Kim, J., Waterston, R.H., & Murray, J.I. (2019). A lineage-resolved molecular atlas of _C. elegans_ embryogenesis at single cell resolution. _Science_, 365(6459), doi:10.1126/science.aax1971.

Pereira, L., Kratsios, P., Serrano-Saiz, E., Sheftel, H., Mayo, A.E., Hall D.H., White, J.G., LeBoeuf, B., Garcia, L.R., Alon, U., & Hobert, O. (2015). A cellular and regulatory map of the cholinergic nervous system of _C. elegans_. _eLife_, 4, e12432. doi:10.7554/eLife.12432.

Picken-Bahrey, H.L. & Moody, W.J. (2003). Early Development of Voltage-Gated Ion Currents and Firing Properties in Neurons of the Mouse Cerebral Cortex. _Journal of Neurophysiology_, 89, 1761-1773.

Pilon, M. & Morck, C. (2005). Development of _Caenorhabditis elegans_ pharynx, with emphasis on its nervous system. Acta Pharmacologica Sinica, 26(4), 396–404.

Portereiko, M.F. & Mango, S.E. (2001). Early morphogenesis of the _Caenorhabditis elegans_ pharynx. _Developmental Biology_, 233, 482–494.

Procko, C., Lu, Y., & Shaham, S. (2011). Glia delimit shape changes of sensory neuron receptive endings in _C. elegans_. _Development_, 138, 1371–1381. 

Rothman, J. & Jarriault, S. (2019). Developmental Plasticity and Cellular Reprogramming in _Caenorhabditis elegans_. _Genetics_, 213(3), 723–757. doi:10.1534/genetics.119.302333.

Rutenberg, J., Cheng, S.M., & Levin, M. (2002). Early embryonic expression of ion channels and pumps in chick and _Xenopus_ development. _Developmental Dynamics_, 225(4), 469-484.

Ryan, K., Lu1, Z., & Meinertzhagen, I.A. (2016). The CNS connectome of a tadpole larva of _Ciona intestinalis (L.)_ highlights sidedness in the brain of a chordate sibling. _eLife_, 5, e16962. doi:10.7554/eLife.16962.

Salkoff, L., Wei, A.D., Baban, B., Butler, A., Fawcett, G., Ferreira, G., & Santi, C.M. (2005). Potassium channels in C. elegans (December 30), WormBook, ed. The C. elegans Research Community, WormBook, doi/10.1895/wormbook.1.42.1, http://www.wormbook.org.

Sarma, G.P., Lee, C-W., Portegys, T., Ghayoomie, V., Jacobs, T., Alicea, B., Cantarelli, M., Currie, M., Gerkin, R.C., Gingell, S., Gleeson, P., Gordon, R., Hasani, R.M., Idili, G., Khayrulin, S., Lung, D., Palyanov, A., Watts, M., & Larson, S.D. (2018). OpenWorm: overview and recent advances in integrative biological simulation of Caenorhabditis elegans. Philosophical Transactions of the Royal Society B, 373, 20170382. doi:10.1098/rstb.2017.0382.

Schafer, W.R. (2005). Deciphering the neural and molecular mechanisms of _C. elegans_ behavior. _Current Biology_, 15(17), R723–R729. doi:10.1016/j.cub.2005.08.020.

Sengupta, P. & Bargmann, C.I. (1996). Cell fate specification and differentiation in the nervous system of _Caenorhabditis elegans_. Developmental Genetics, 18(1), 73-80.

Simaan, M. & Cruz, J.B. (1973). On the Stackelberg Strategy in Nonzero-Sum Games. _Journal of Optimization Theory and Applications_, 11(5), 533–555.

Sokolchik, I., Tanabe, T., Baldi, P.F., & Sze, J.Y. (2005). Polymodal sensory function of the _Caenorhabditis elegans_ OCR-2 channel arises from distinct intrinsic determinants within the protein and is selectively conserved in mammalian TRPV proteins. _Journal of Neuroscience_, 25(4), 1015-1023.

Sulston, J.E., Schierenberg, E., White J.G., & Thomson, J.N. (1983). The embryonic cell lineage of the nematode _Caenorhabditis elegans_. _Developmental Biology_, 100, 64-119. 

Sulston, J.E. & Horvitz, H.R. (1977). Postembryonic cell lineages of the nematode _Caenorhabditis elegans_. _Developmental Biology_, 56, 110-156. 

Takagi, K. (2017). A distribution model of functional connectome based on criticality and energy constraints. _PLoS One_, 12(5), e0177446.

Taylor, R.W., Hsieh, Y-W., Gamse, J.T., & Chuang, C-F. (2010). Making a difference together: reciprocal interactions in _C. elegans_ and zebrafish asymmetric neural development. _Development_, 137(5), 681–691.

Towlson E.K., Vertes, P.E., Ahnert, S.E., Schafer, W.R., & Bullmore, E.T. (2013). The rich club of the _C. elegans_ neuronal connectome. _Journal of Neuroscience_, 33(15), 6380-6387. doi: 10.1523/JNEUROSCI.3784-12.2013.

UniProt Consortium (2019). UniProt: a worldwide hub of protein knowledge. _Nucleic Acids Research_, 47, D506-515. https://www.uniprot.org/uniprot/Q7JPF0

Usuyama, M., Ushida, C., & Shingai, R. (2012). A Model of the Intracellular Response of an Olfactory Neuron in _Caenorhabditis elegans_ to Odor Stimulation. _PLoS One_, 7(8), e42907. doi:10.1371/journal.pone.0042907.

Varier, S. & Kaiser, M. (2011). Neural Development Features: spatio-temporal development of the _Caenorhabditis elegans_ neuronal Network. _PLoS Computational Biology_, l7(1), e1001044. doi:10.1371/journal.pcbi.1001044

Varshney, L.R., Chen, B.L., Paniagua, E., Hall, D.H., & Chklovskii, D.B. (2011). Structural properties of the _Caenorhabditis elegans_ neuronal network. _PLoS Computational Biology_, 7(2), e1001066. doi:10.1371/journal.pcbi.1001066

Walker, D.S., Chew, Y.L., & Schafer, W.R. (2018). Genetics of Behavior in _C. elegans_. In "The Oxford Handbook of Invertebrate Neurobiology". J.H. Byrne ed., pgs. 1-38. Oxford University Press, Oxford, UK. doi:10.1093/oxfordhb/9780190456757.013.

Windoffer, R. & Westheide, W. (1988). The Nervous System of the Male Dinophilus gyrociliatus (Polychaeta, Dinophilidae):11. Electron Microscopical Reconstruction of Nervous Anatomy and Effector Cells. _The Journal of Comparative Neurology_, 272, 475-488.

White, J.G., Southgate, E., Thomson, J.N., & Brenner, S. (1986). The structure of the nervous system of the nematode _Caenorhabditis elegans_. _Philosophical Transactions of the Royal Society B_, 314(1165), 1-340. doi:10.1098/rstb.1986.0056.

White, J.G., Albertson, D.G., & Anness, M.A. (1978). Connectivity changes in a class of motoneurone during the development of a nematode. _Nature_, 271, 764–766.

Wu, Y., Ghitani, A., Christensen, R., Santella, A., Du, Z., Rondeau, G., Bao, Z., Colon-Ramos, D., & Shroff, H. (2011). Inverted selective plane illumination microscopy (iSPIM) enables coupled cell identity lineaging and neurodevelopmental imaging in _Caenorhabditis elegans_. _PNAS_, 108(43), 17708-17713.

Zega, G., Thorndyke, M.C., & Brown, E.R. (2006). Development of swimming behaviour in the larva of the ascidian Ciona intestinalis. _The Journal of Experimental Biology_, 209, 3405-3412.

Zheng, C. & Chalfie, M. (2016). Securing Neuronal Cell Fate in _C. elegans_. _Current Topics in Developmental Biology_, 116, 167-180. doi:10.1016/bs.ctdb.2015.11.011.




