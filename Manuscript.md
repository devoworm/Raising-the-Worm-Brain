## Raising the Connectome: the emergence of neuronal activity and behavior in _C. elegans_

### Abstract
The differentiation of neurons and formation of connections between cells is the basis of both the adult phenotype and behaviors tied to cognition, perception, reproduction, and survival. Such behaviors are associated with local (circuits) and global (connectome) brain networks. A solid understanding of how these networks emerge is critical. Here, we provide a guided tour of early developmental events in their electrophysiological context. We demonstrate the transition from developmental cells to terminally differentiated cells as being defined by functional changes that set up adult behavioral function. In a model organism such as _C. elegans_, this transition is developmentally conserved and well-characterized in various ways by publicly-available data. In this paper, we will build on an existing time-series model of neuronal differentiation and conduct a functional assessment of this developmental connectome. Multiple sources of data will be brought to bear on this effort, providing information about the emerging connectome as well as the emergence of functional subnetworks. A first-mover model of the emerging connectome is also introduced, which will help to synthesize the details of our results. The broader implications of these functional analyses will be considered, including implications for computational modeling and behavioral origins.

### Introduction
The field of connectomics has provided opportunities to view the structure and function of nervous systems in a new light. The proliferation of data for small connectomes such as those found in the nematode _Caenorhabditis elegans_ allows us to study the connected nervous system at both the single cell and systems level (Berck et.al, 2016; Eichler et.al, 2017; Ko et.al, 2013). In addition, emerging functional perspectives on genomic contributions (Barabasi and Barabasi, 2020) and statistical regularities (Takagi, 2017) of the connectome allow for a flexible, multiscale model of biology and behavior. In this paper, this perspective will be used to better understand the potential functional role of ion channels among terminally-differentiated neurons present at various points in embryogenesis. Based on these partial patterns of adult connectivity, generalizations can be made with respect to the structural and functional features of a developing connectome (Kaiser, 2017). These relationships tend to be conserved over developmental time, and changes due to postembryonic changes and larval plasticity are minimal. 

A parallel area of inquiry will be defined by the differentiation of developmental cells and the acquisition of their terminally-differentiated neuronal states. Far from being a switch operating at a discrete point in time, differentiation of developmental cells into neurons involves two sets of transcription factors: so-called terminal selectors (Hobert, 2016a) and protectors/stabilizers (Zheng and Chalfie, 2016). In the case of the former, transcriptional mechanisms serve to simultaneously initiate and maintain cell fate choice. Protector/stabilizers then ensure the smooth, uninterrupted expression of terminal selectors. The notion that neuronal differentiation is a complex process that unfolds over time is most important to the context of emerging connectomes. Therefore, it is imperative that details regarding the so-called neuronal identity of these newly-integrating cells be understood in order to predict the emergence of physiology and ultimately behavior (Hobert, 2016b). 

A third area of inquiry involves exactly when and under what conditions these terminally-differentiated neurons begin to produce organismal-level behaviors. It has been suggested that structural features emerge earlier in development than functional features (Cao et.al, 2016). As we will see, the first neuronal cells emerge well after the first synaptic connections between cells are established, which in turn is decoupled from the emergence of the first behaviors. Our contribution to this understanding is to flesh out the structure of this timing relative to differentiation events. This includes making connections between the terminal differentiation of specific neurons, their electrical and molecular milieu, and the systems-level significance of the temporal process. Hopefully, this brings us closer to understanding the tempo and scope of morphogenesis relative to the adult phenotype.   

One way to unify these sets of questions is by making reasonable assumptions about development from data collected in adult animals. _Caenorhabditis elegans_ is the perfect choice for this approach due to its straightforward developmental trajectory. While there has been limited work done on the emergence of electrophysiology and electrical connectivity during the course of _C. elegans_ embryogenesis, we can use a combination of data science and mathematically-based conceptual modeling to shed light on these relationships. An abundance of quantitative data also allows for inference to proceed using the lineage tree and adult end state in tandem to simulate intermediate developmental phenotypes.

In this paper, we provide a guided tour of early developmental events in electrophysiological context, along with a systems-level perspective on the electrophysiological milieu of the _C. elegans_ connectome. Such a perspective is lacking in the _C. elegans_ literature, and it should be broadly applicable to the study of developmental dynamics. We will build on the work done in Alicea (2018), where the construction of partial connectomes for multiple time points in embryonic development demonstrates how the neuronal networks emerge from developmental cells. We will also consider emerging neuronal networks as constituents of functional networks observed in the adult phenotype. Using information from multiple sources, we are able to fill in details along a timeline that spans from the birth of the first neuron to the emergence of the first behaviors. To make the connection between molecular biology, cell biology, and behavior, analogies can be made using both adult neuronal function and simulation methods.  

#### Justification of the _C. elegans_ model
This endeavor focuses on the _C. elegans_ connectome, and there are a number of reasons why limiting the analysis to this connectome is more illuminating than a broad cross-species study. The first of these is the deterministic nature of _C. elegans_ neurodevelopment. _C. elegans_ offers a clear mapping between developmental cell lineages, differentiating neurons in the embryo, and the adult phenotype. Secondly, this connectome is small but also functionally diverse, consisting of 302 neurons in the hermaphrodite (White et.al, 1986) and 385 cells in the male (Cook et.al, 2019). Related to this, all cells in the _C. elegans_ connectome have a known function. A lack of functional ambiguity also provides us with both well-established patterns of connection and well-defined structural features (Varshney et.al, 2011). Finally, there is a well-established community of open resources that allow for multifaceted bioinformatic investigations.  
The _C. elegans_ model also allows us to look at developmental cell lineages (Sulston et.al, 1983) along with events that precede the emergence of the first neuronal cells. Figure 1 shows a complex distribution for the birth of developmental cells across the so-called first proliferation phase (Altun and Hall, 2011). While the birth of developmental cells occurs in aperiodic bursts during this interval, there are three bursts of particularly interest to our sampling of neuronal cell births. The first burst of births are shown in red, and occur from 210 to 285 minutes. Next is a burst of developmental cell births shown in orange, and occurs from 285 to 345 minutes. While there are no developmental cell births from 345 to 365 minutes, there is a third burst of births from 365-400 minutes of embryogenesis. Based on a prior analysis of the data (Alicea et.al, 2019), bursts of developmental cell births may precede rounds of neurogenesis. 

Even though _C. elegans_ has a deterministic developmental trajectory with respect to cell lineage and identity, this potential relationship is not straightforward. _C. elegans_ neurons undergo a multipotency-to-commitment transition (MCT), in which neuronal cells are born from a diverse developmental cell lineage that also gives rise to muscle and epithelial cells (Rothman and Jarriault, 2019). This may provide a basis for great electrophysiological diversity across cells in very distinct subcircuits relevant to behavior. As we will see, there is a difference between functional asymmetry and cell lineage asymmetry which is partially driven by the expression and function of ion channels.

<p align="center">
  <img width="256" height="227" src=""><BR>
  <b>Figure 1.</b> Developmental precursors to the first connectome cells to terminally-differentiate in the embryo. Data are arranged as a histogram with bins of size 8. Red, Orange, and Gray bars are bins of particular interest to our sampling scheme.
</p>
  
The aggregate measure shown in Figure 1 is consistent with the finding that cellular specialization is coordinated with rounds of cell division, although this does not result from a specific cell division-related mechanism (Alberts et.al, 2002). In conceptually separating the functional networks from structural networks, we find that different neuronal properties can provide alternate views of the developing connectome. For example, transcription factors define _C. elegans_ neurons more distinctly than the 118 neuron classes defined by 118 neurons classes based on anatomical and synaptic connectivity (Hobert, 2016). Nevertheless, we do see that the first few neurons and major expansion in the number of neurons occur immediately after the first two bursts of developmental cell proliferation.

#### Ion Channels in _C. elegans_
We take the perspective that ion channels are critical to the embryonic, larval, and adult stages of life-history. In terms of the _C. elegans_ nervous system, the larval stage exhibits the greatest plasticity of all life-history stages. In this paper, however, we are limiting our survey to ion channel expression in terminally-differentiated neurons. While little is known about functional ion channel expression in developmental cells, our goal is to identify the ion channels expressed in terminally-differentiated neurons on the way to adult behavioral function. While there are select studies on how membrane current is regulated in specific neuronal cell types in postembryonic development (for an example from AIY interneurons, see Faumont et.al, 2006), there are no system-wide surveys on the topic. Variation in ion channel expression can occur in three ways: synaptic pruning during sexual differentiation (Oren-Suissa et.al, 2016), defined mutant phenotypes (Jorgenson and Mango, 2002), and generalized phenotypic plasticity (Jin and Qi, 2018). In terms of phenotypic plasticity, an adaptive response generally occurs in postembryonic stages of development such as L1 (DD1 remodeling, see White, 1978) or dauer (Procko et.al, 2011). More generally, we can observe adaptive plasticity throughout larval development and adulthood in specific functional circuits, such as the mechanosensory circuit (Bozorgmehr et.al, 2013). 

#### Outline of Approach
This analysis in this paper will involve four basic components. The first of these involves an analysis of cells at different points in time (Alicea et.al, 2018), allowing for an inventory of the various tissue and organ types represented by newly differentiated neurons. Ion channel data collected from WormBase (Harris et.al, 2019) will be used to identify key genes, associated cells, and annotations. Determining the relationships between functional gene identities, specific ion channels, and functional annotations will be enhanced by using data sets (see Methods) developed at the OpenWorm Foundation (Sarma et.al, 2018). This analysis yields information regarding ion channel types present at a specific time point in embryogenesis. In terms of the latter, the data set featured in (Packer et.al, 2019) can be used in conjunction with annotation metadata and embryonic gene expression information to draw conclusions regarding the phylogenetic and developmental origins of the connectome. Of particular interest is the link between ion channels expressed by neuronal cells present in the embryo and the lineage-specific expression of ion channel-related and other associated genes. The final component relies upon how stereotypical C. elegans behaviors are heavily influenced by genetics to establish a link between the presence of certain neurons and the potential for early forms of chemosensation, thermosensation, and even learning and memory (Walker et.al, 2019).

### Methods

#### OpenWorm Resources
An annotated collection of terminally-differentiated cell function was used as an initial query of which cells are associated with which ion channels. The ChannelWorm dataset is courtesy of Vahid Ghayoomie and Gopal Sarma of the ChannelWorm project (https://github.com/openworm/ChannelWorm/). Functional annotations are courtesy of Stephen Larson and Mark Watts from the PyOpenWorm project. The DevoWorm group has assembled a number of bioinformatic conversions that have been used to track the birth times and developmental lineage of each cell in the C. elegans connectome. These data can be found on Github (https://github.com/devoworm/DevoWorm) and the Open Science Framework (Alicea, 2018). All projects are sponsored by the OpenWorm Foundation (http://openworm.org).

#### First-mover Model Repository
All notes, figures, and code associated with the first-mover model are located in a Github repository (https://github.com/devoworm/Raising-the-Worm- Brain).

__VisCello.__ To discover further relationships between gene expression and ion channel expression in individual cells, we utilized the VisCello database (Packer et.al, 2019) which can be explored using a standalone app downloadable from Github (https://github.com/qinzhu/VisCello.celegans) or interactively via Shiny app (https://cello.shinyapps.io/celegans_explorer/). Plots produced using VisCello are produced using the UMAP (Uniform Manifold Approximation and Projection) method (https://umap-learn.readthedocs.io/en/latest/how_umap_works.html), which maps data points to a two-dimensional manifold (McInnes et.al, 2018). A form of dimensionality reduction that relies upon Topological Data Analysis, UMAP preserves global structure in the data, and uses graphical separation between related points to describe this structure.

__WormBase.__ Supplemental information about protein expression and cells of interest are retrieved from WormBase Version:WS273 (https://www.wormbase.org/). WormBase (Harris et.al, 2019) is a C. elegans community resource that allows us to map between specific adult cells.

### Results
This analysis will proceed by walking through the developmental connectome as it exists at five points during embryogenesis: 265, 280, 290, 300, and 400 minutes post-fertilization. These networks are defined in Alicea (2018), and are derived from information regarding the birth time of terminally-differentiation neurons rather than direct observations of connectivity. In addition to cells that are connected by common time of birth, subnetworks defined in the literature in terms of physiological function (particularly the NSY-5 subnetwork) will be analyzed. Figure 2 contains a timeline that shows major events of embryonic development in context. 

For each timepoint, the newly terminally-differentiated neurons are defined and matched to known ion channels from the ChannelWorm database. Information about gene expression and other attributes of selected cells are then verified using the WormBase resource. Transcription activity is assessed for interesting relationships are also presented based on queries of the VisCello database. Finally, a model of first-mover dynamics is introduced to clarify the developmental process with respect to an expanding neuronal network.

#### Ion channels for cells present at 265 minutes
At 265 minutes, we have one asymmetric cell that emerges: RMEV. According to the ChannelWorm database, there is only one associated ion channel (AVR-15). RMEV is a ring motor neuron, and does not have a bilateral partner. A search of RMEV in WormBase reveals expression of two nervous system-associated genes: ntr-2 and msi-1. While neither of these explicitly code for ion channels, both genes are confirmed to exhibit generic nervous system function. ntr-2 is expressed in both ADL sensory neurons and RMED, and is associated with G-protein coupled receptor activity. By contrast, msi-1 is known to be expressed in adult AVA and AFD neurons. 
  
The ion channel AVR-15 has an important role in C. elegans motor function and behavior. AVR-15 is a glutamate-gated chloride channel subunit (Dent, 1997), and avr-15 genetic mutants are known to lack neurotransmission by the M3 motor neuron, which controls the pharyngeal muscle (Avery, 1993). According to Gendrel et.al (2016), both RMEV and M3 form part of the GABAergic nervous system in C. elegans, which constitutes nearly half of the adult C. elegans connectome. 

#### Ion channels for cells present at 280 minutes
For the 280 minute connectome, there are five terminally-differentiated neurons: RMEV (born at 265 minutes), and two symmetric pairs of neurons (ADFL/R and AWBL/R). Since the latter four neurons are bilateral pairs, each set share functions and thus ion channel associations. The ChannelWorm database shows three ion channel-protein associations for ADFL and ADFR: OCR-2, MGL-3, and KVS-1. OCR-2 is a transient receptor potential channel (TRPV) protein that regulates serotonin in chemosensory and olfactory functions (Sokolchik, 2005), MGL-3 is a building block in G-protein coupled receptors for Glutamate (Hobert, 2005), and KVS-1 protein expression is involved in building voltage-gated potassium channel complexes that are associated with a variety of functions (Uniprot Consortium, 2019). 

<p align="center">
  <img width="256" height="227" src=""><BR>
  <b>Figure 2.</b> Timeline that shows major events in <i>C. elegans</i> embryogenesis from fertilization (0 minutes) to hatch from the egg (800 minutes).
</p>
  
ADFL and ADFR have been identified as chemosensory sheath cells that detect volatile compounds (Bargmann, 2006). Looking back at Figure 2, this represents the emergence of components in a functional circuit well before there any environmental or activity-dependent signals to shape their fate. As harbingers of neuronal function, AWBL and AWBL are also important for their role in the NSY-5 network. NSY-5, a protein resulting from expression of the inx-19 gene, forms a gap junction network during embryogenesis with 32 other cells in the nervous system (Chuang et.al, 2007). About half of these cells share the same lineage, and the NSY-5 network as a whole is required for stochastic, asymmetric gene expression (Alqadah et.al, 2016). Aside from the potential importance of this subnetwork for regulation of the developmental connectome, WormBase associates inx-19 expression is associated with calcium channel inhibition.  
Ion channels for cells present at 290 minutes

The 290 minute connectome expands to 38 terminally-differentiated neurons in various anatomical locations (see Figure 3). There are a number of neuronal pairs born during this time, as well as several asymmetric terminal-differentiation events. We can focus on two groups (AV and IL2) to appreciate the functional architecture established at this point in development. In terms of AV neurons born at 290 minutes of development (AVDL, AVDR, AVJL, AVJR, AVKL, AVKR, AVL), there are several proteins associated with these cells that play a role in ion channel expression. These include UNC-36, GLR-1, NMR-1, and MEC-10. GLR-1 are involved in the formation of glutamate signalling, while NMR-1 and MEC-10 are involved in NMDA signalling and mechanosensory function, respectively. 

On the other hand, IL2 neurons (IL2DL, IL2DR, IL2L, IL2R, IL2VL, IL2VR) begin to form the inner labial structure of the head, and play a functional role in larval plasticity, in particular enhanced sensory capabilities during Dauer formation (Androwski et.al, 2017). IL2 expresses proteins such as OSM-9 and EGL-2. The former protein (OSM-9) has been implicated in a feeding behavior called osmotic avoidance (Hallam and Sternberg, 2008). More generally, IL2 has been implicated in nictation and dispersal behaviors during the dauer stage (Albert and Riddle, 1983). IL2 neurons originate from the ABal and ABar sublineages (WormBase, also see Wu et.al, 2011).

#### Ion channels for cells present at 300 minutes
One cell pair that emerge at 300 minutes post-fertilization is AWCL/R. These are the Amphid Wing C neurons that are essential for olfaction and form the basis for the NSY-5 subnetwork. AWCL/R neurons are unique among C. elegans olfactory receptors as they exhibit a fluctuation of intracellular calcium ions consistent with odorant stimulation, particularly the presentation and removal of the stimulus (Chalasani et.al, 2007). A computational model has demonstrated that the AWC cell pair are susceptible to noise, even when ion channels that mediate Ca2+ influx were included (Usuyama et.al, 2012).
  
In terms of setting up a functional circuit, AWCL/R olfactory neurons work cooperatively with AIBL/R and AIYL/R interneurons to form an adaptive unit that responds to food and odorants (Chalasani et.al, 2007). In both larvae and adults, AWCL/R cells can inhibit AIYL/R cells via glutamate-gated chloride channels. The presentation of an olfactory stimulus can act to override this inhibition of AIYL/R cells. From our terminal differentiation temporal data, we can see that while AIBL/R and AWCL/R are born at 300 minutes, the AIYL/R interneuron does not appear until our 400 minutes sampling time. Whether these functional differences are influenced by these differences in birth times is not known.

<p align="center">
  <img width="256" height="227" src=""><BR>
  <b>Figure 3.</b> Distribution of cell types (based on families in Alicea et.al, 2019) born at 290 minutes.
</p>

#### Ion channels for cells present at 400 minutes
A total of 87 new neurons differentiate between the 300 and 400 minute sampling intervals. Table 1 shows (by cell family) all new cells that occur in the 400 minute sampling interval that are not present in the 300 minutes sampling interval. The most abundant newly-differentiated neuronal families include members of the AV family (14 cells), RI family (9 cells), RM family (7 cells), and UR family (6 cells). 

Our 400 minute sampling interval also reveals the diversity of timing among inner labial (IL) neurons. For example, IL2 neurons are born at 290 minutes, whereas IL1 neurons appear at 400 minutes of embryogenesis. Despite this, each pair of neurons are cholinergic polymodal neurons (Pereira et.al, 2015) that have multiple mechanosensory functions (Goodman, 2006). Yet according to WormBase, only IL1 expresses DELM-1 and DELM-2 sodium channels. While expression of these channels in IL1 neurons enables mechanosensation at the organismal level, mechanosensation only becomes important later in development (post-hatch). As mentioned during the 280 minute analysis, we see neurons that form a functional circuit emerge well before the associated behaviors themselves. 

#### Gene expression at 250 minutes
Before moving on to the origins of functional subnetworks, let us examine the developmental source of neurons using a lineage-resolved single cell molecular atlas called VisCello (Packer et.al, 2019). Figure 4 demonstrates these cell type distinctions, as defined by single-cell transcriptomics signatures of each cell identity. These visualizations demonstrate both the nature and shape of this variation. One main finding of this approach is that the differentiation process decouples the identity of developmental lineage from the transcriptional activity of terminally-differentiated cells (Packer et.al, 2019). In other words, cells from identical developmental sublineages can acquire divergent transcriptional profiles upon differentiation.


<b>Table 1.</b> Schematic of first-mover dynamics. A: a simple relationship between endogenous processes and inputs, B: a potential first-mover strategy for intrinsic circuits (time of birth in hypothetical minutes), C: transformation from circles (that constitute networks) to boxes.


#### Timing of NSY-5 subnetwork
Due to a number of functional attributes, the innexin-dependent NSY-5 network is worth examining in more detail. As opposed to our time-threshold networks, neurons included in this network are defined by their expression of NSY-5 (Chuang et.al, 2007). The first neurons in this network appear at 280 minutes, and continue to appear until after 400 minutes post-fertilization. At least one set of neurons in this network (AWCL/R, or Amphid Wing C cells) are influenced by calcium influx through voltage-gated calcium channels (Hseih et.al 2014). In particular, the NSY-5 network is required for left/right gene expression asymmetry in AWC neurons. Overall, this network consists mainly of cells associated with Amphid Sheath and Neuropil, or function as Interneurons and Sensory Neurons. While the left-right asymmetry of cell differentiation is somewhat uncommon (about 1/3rd of all terminally-differentiatied cells) in _C. elegans_, functional asymmetry for properties such as gene expression is much more common (Hobert et.al, 2002). Among AWC neurons, functional asymmetry is much more common than birth asymmetry, which is greater than 50 minutes in only two pairs of NSY-5 cells (ASHL/R and PVQL/R). By comparison, symmetric induction of NSY-5 in AWC neurons occurs 150 minutes after their birth time, which is well after birth time but still falls within pre-hatch development (Taylor et.al, 2010). 

<p align="center">
  <img width="256" height="227" src=""><BR>
  <b>Figure 4.</b> Developmental cells born at 250 minutes that contribute to all future cell types and tissues (A) and neurons and glia (B) more specifically. v1 and v2 represent the dimensions of a two-dimensional projection of the source data. Distance on these manifolds are defined by single-cell transcriptional profiling of all cells.
</p>
  
#### Potassium channels in development
Another set of developmental events that are a critical component of neuronal function and survival to adulthood is the expression of potassium (K<sup>+</sup>) channels. While K+ channels are expressed in every adult _C. elegans_ cell, neurons express the 6TM, voltage-gated channels Kv1, Kv2, Kv3, and Kv4. The existence of potassium channel mutant phenotypes demonstrates that these channels allow for the complex electrophysiology that drives neuronal activity (Salkoff et.al, 2005). Voltage-gated channels not only allow for the generation of action potentials (Mellem et.al, 2008), but the generation of spontaneous electrical activity as well.

Salkoff et.al (2005) refers to K<sup>+</sup> channels as transistors that enable the regulation of physiological function. In general, spontaneous activity can be quite variable during development, and affect a number of functions including synaptic connectivity. This activity is controlled by two factors: inputs from other neurons (via either synapses or gap junctions) and intrinsic ion channel properties (Picken-Bahrey and Moody, 2003). Functional asymmetry in the _C. elegans_ connectome is driven by both of these factors which can be approximated using a first-mover model. 

#### Critical neurons and their cholinergic expression
Now we will turn to the intersection of network functionality and the role of cholinergic neurons. Through a series of computational experiments, Kim et.al (2016) have identified 12 neurons that are critical for connectome function and involves 29 critical synapses. Critical neurons are highly connected compared with other neurons in the same network, and serve to bridge between different modules and reduce the overall number of connections across the connectome. Such neurons are central to a connectome and must be present in order for the various subnetworks of an adult connectome to remain functional. In the face of environmental challenges and mutation, these cells enable the connectome to remain resilient (Gao et.al, 2016) without evolving new innovations. Nine of these 12 critical neurons are born in the hermaphrodite connectome prior to the initiative of the twitching phase (470 minutes). Six of these nine cells have cholinergic function: AVAL/R, PVCL/R, PVPR, and AVER. All of these cells are positive for unc-17/cha-1 and cho-1 expression (Pereira et.al, 2015). These cells also express _C. elegans_ homologues of ACE genes (Schaefer, 2005), which are associated with a host of diverse functions. 

Towlson et.al (2015) have identified a core set of rich club neurons, which also serve as critical for connectome function. This set of 11 cells differs slightly from the Kim et.al (2016) list, and also include cholinergic neurons AVBL/R, AVDL/R, and AVEL. The map of Pereira et.al (2015) shows that not only are these cells ventral cord interneurons with cholinergic function, they also receive ACh inputs from other cells. It is not clear whether there are additional molecular and/or electrophysiological properties that differentiate rich club neurons from other neurons in the connectome in an a priori manner, but hierarchical relationships with other neurons in the connectome can be approximated using a first-mover model. 

#### Events that occur post-400 minutes
There are a number of events that occur after the 400-minute mark that are relevant to neuronal function. The 400 minute mark defines the beginning of the comma stage of development, where the head becomes thicker than the body and elongates correspondingly (Christensen et.al, 2015). While the anatomical distribution of neurons generally remain conserved throughout development (Nicosia et.al, 2013; Alicea, 2017), a number of post 400-minute transformations define connectivity and ultimately organismal-level behaviors. These transformations are often connected to the increasing asymmetry in phenotype as the spherical egg becomes an asymmetrical organism (Gordon and Gordon, 2016).

The first of these events is the first evidence of axonal outgrowth (see Figure 3), at approximately 450 minutes post-fertilization (Morck et.al, 2003; Taylor et.al, 2010). From about this time until hatch (800 minutes; Sulston et.al, 1983), we observe the onset of asymmetric gene expression in symmetric pairs of neurons. This is particularly important for neurons constituting the NSY-5 network (Hobert et.al, 2002; Taylor et.al, 2010). Along with this asymmetry in gene expression, there is also an increasing asymmetry of phenotype as the hypodermis, muscle syncytium, and intestines all begin to take shape. This period between the embryonic neuronal birth and the onset of connectome-related behavior is an interesting period of time which we will approximate using a first-mover model.

#### First-mover Model of Developmental Dynamics
In the case of potassium channel subnetworks, criticality in embryogenetic connectomes, and the period between neuronal birth and the onset of connectome-related behaviors, the use of a first mover model was suggested. Therefore, a first-mover model of developmental emergence will now introduced to tie together many of these developmental processes. First-mover dynamics are based on the principle of Stackleberg competition (Simaan & Cruz, 1973), and can be represented by a generic abstraction of connectome development not based on any particular organism. It is meant to capture the process of morphogenesis and associated interactions defining the transition from emerging structure to organized function. The first-mover game theoretic model of development was first proposed in Stone et.al (2018) and is used here to represent the potential order of interactions between the emergence of newly-born neurons, asymmetric ion channel expression amongst bilateral pairs, and the formation of neural circuits. 
  
The first mover model describes neurons that emerge and connect in an expanding network (see Figure 5). Each cell is born at a certain time point in development with a pre-programmed set of ion channels with endogenous expression (without any cues external to the cell). In this example, cells that are born first control the expression of cells that are born later upon connection with one another by serving as an input to the endogenous activity. A pair of neurons connected in this way is called an intrinsic circuit. Each intrinsic circuit can be modeled as a sequential game that can be modeled using an extensive form representation (e.g. decision tree). In this instance, a single move is a connection between two cells, initiated by the first mover. An example of this is shown in Figure 5B, where four moves are ordered sequentially. The cell born at 280 minutes makes two sequential moves, followed by a move made by a cell born at 300 minutes (and connected to during the first move). This defines the structure within which subsequent moves will be made.

<p align="center">
  <img width="256" height="227" src=""><BR>
  <b>Figure 5.</b> Schematic of first-mover dynamics. A: a simple relationship between endogenous processes and inputs, B: a potential first-mover strategy for intrinsic circuits (time of birth in hypothetical minutes), C: transformation from circles (that constitute networks) to boxes.
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

As the _C. elegans_ connectome is considered analytically tractable, we hope that the extraction and analysis of neuronal populations at different points in embryonic development can be applied to other small connectomes (<1000 neurons). The polycheate (Windoffer & Westheide, 1988; Hochberg, 2009) and the larval tunicate Ciona intestinalis (Bezares-Calderon & Jekely, 2016; Ryan et.al, 2016) are two such examples. The tunicate model is especially interesting, as it provides an opportunity to study asymmetry. Yet we also see how the emergence of behaviors are context-specific, as swimming in _C. intestinalis_ (Zegal et.al, 2006) emerges in a way that is fundamentally different from behaviors such as pharyngeal pumping in _C. elegans_.

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


### Footnotes
<sup>1</sup> Curation of selected resources are courtesy of Vahid Ghayoomie and Gopal Sarma of the ChannelWorm project (https://github.com/openworm/ChannelWorm/) sponsored by the OpenWorm Foundation (http://openworm.org).


### References
Albert, P.S. & Riddle, D.L. (1983). Developmental alterations in sensory neuroanatomy of the Caenorhabditis elegans dauer larva. Journal of Comparative Neurology, 219(4), 461-481. doi:10.1002/cne.902190407.

Alberts, B., Johnson, A., Lewis, J., Raff, M., Roberts, K., & Walter, P. (2002). Caenorhabditis Elegans: Development from the Perspective of the Individual Cell. In "Molecular Biology of the Cell", 4th edition. Garland Science, New York. https://www.ncbi.nlm.nih.gov/books/NBK26861/

Alicea, B., Gordon, R., & Portegys, T.E. (2019). Data-theoretical Synthesis of the Early Developmental Process. bioRxiv, doi:10.1101/282004.

Alicea, B., Gordon, R., & Banerjee, A. (2018). Dataset: Embryo networks and connectomes in Caenorhabditis elegans. doi:10.17605/OSF.IO/Q9JVB. https://osf.io/q9jvb/

Alicea, B. (2017). The emergent connectome in Caenorhabditis elegans embryogenesis. BioSystems, 173, 247-255.

Alqadah, A., Hsieh, Y.W., Xiong, R., & Chuang, C.F. (2016). Stochastic left-right neuronal asymmetry in Caenorhabditis elegans. Philosophical Transactions of the Royal Society of London B, 371(1710), 20150407.

Androwski, R.J., Flatt, K.M., & Schroeder, N.E. (2017). Phenotypic plasticity and remodeling in the stress-induced C. elegans dauer. Wiley Interdisciplinary Reviews: Developmental Biology, 6(5). doi:10.1002/wdev.278.

Ardiel, E.L., Kumar, A., Marbach, J., Christensen, R., Gupta, R., Duncan, W., Daniels, J.S., Stuurman, N., Colon-Ramos, D., & Shroff, H. (2017). Visualizing calcium flux in freely moving nematode embryos. Biophysical Journal, 112, 1975–1983.

Avery L. (1993). Motor neuron M3 controls pharyngeal muscle relaxation timing in Caenorhabditis elegans. Journal of Experimental Biology, 175, 283-297.

Avery, L., & Horvitz, H.R. (1989). Pharyngeal pumping continues after laser killing of the pharyngeal nervous system of C. elegans. Neuron, 3, 473–485.

Azevedo, R.B.R. & Leroi, A.M. (2001). A power law for cells. PNAS, 98(10), 5699–5704.

Barabasi, D.L. & Barabasi, A-L. (2020). A Genetic Model of the Connectome. Neuron, 105, 1–11.

Barabasi, A-L. & Albert, R. (1999). Emergence of scaling in random networks. Science, 286(5439), 509–512.

Bargmann, C.I. (2006). Chemosensation in C. elegans, WormBook. The C. elegans Research Community (eds). WormBook, doi/10.1895/wormbook.1.123.1. 

Bateson, P. & Laland, K.N. (2013). Tinbergen’s four questions: an appreciation and an update. Trends in Ecology and Evolution, 28(12), 712-718.

Berck, M.E., Khandelwal, A., Claus, L., Hernandez-Nunez, L., Si, G., Tabone, C.J., Li, F., Truman, J.W., Fetter, R.D., Louis, M., Samuel, A.D., & Cardona, A. (2016). The wiring diagram of a glomerular olfactory system. eLife, 13, 5.

Betzel, R.F., Avena-Koenigsberger, A., Goni, J., He, Y., de Reus, M.A., Griffa, A., Vertes, P.E., Misic, B., Thiran, J-P., Hagmann, P., van den Heuvel, M., Zuo, X-N., Bullmore, E.T., & Sporns, O. (2016). Generative models of the human connectome. Neuroimage, 124(A), 1054–1064.

Bezares-Calderon, L.A. & Jekely, G. (2016). Think small. eLife, 5, e22497. doi:10.7554/eLife.22497.

Bhattacharya, A., Aghayeva, U., Berghoff, E.G., & Hobert, O. (2019). Plasticity of the electrical connectome of C. elegans. Cell, 176(5), 1174-1189. doi:10.1016/j.cell.2018.12.024. 

Bianconi, G., Barabasi, A.L. (2001). Competition and multiscaling in evolving networks. Europhysics Letters, 54(4), 436–442.

Bozorgmehr, T., Ardiel, E.V., McEwan, A.H., & Rankin, C.H. (2013). Mechanisms of plasticity in a Caenorhabditis elegans mechanosensory circuit. Frontiers in Physiology, 4, 88.

Braitenburg, V. (1984). Vehicles: experiments in synthetic Psychology. MIT Press, Cambridge, MA.

Cao, M., Huang, H., Peng, Y., Dong, Q., & He, Y. (2016). Toward Developmental Connectomics of the Human Brain. Frontiers in Neuroanatomy, 10, 25. doi: 10.3389/fnana.2016.00025.

Chalasani, S.H., Chronis, N., Tsunozaki, M., Gray, J.M., Ramot, D., Goodman, M.B., & Bargmann, C.I. (2007). Dissecting a circuit for olfactory behaviour in Caenorhabditis elegans. Nature, 450(7166), 63-70.

Chisholm, A.D. & Hardin, J. (2005). Epidermal morphogenesis. WormBook, ed. The C. elegans Research Community. WormBook, doi/10.1895/wormbook.1.35.1.

Christensen, R.P., Bokinsky, A., Santella, A., Wu, Y., Marquina-Solis, J., Guo, M., Kovacevic, I., Kumar, A., Winter, P.W., Tashakkori, N., McCreedy, E., Liu, H., McAuliffe, M., Mohler, W., Colon-Ramos, D.A., Bao, Z., & Shroff, H. (2015). Untwisting the Caenorhabditis elegans embryo. eLife, 4, e10070 doi:10.7554/eLife.10070.

Chuang, C.F., Vanhoven, M.K., Fetter, R.D., Verselis, V.K., & Bargmann, C.I. (2007). An innexin-dependent cell network establishes left-right neuronal asymmetry in C. elegans. Cell, 129(14), 787-789.

Clement, P. (1987). Movements in rotifers: correlations of ultra-structure and behavior. Hydrobiologia, 14, 339–359.

Cook, S.J., Jarrell, T.A., Brittin, C.A., Wang, Y., Bloniarz, A.E., Yakovlev, M.A., Nguyen, K.C.Q., Tang, L.T-H., Bayer, E.A., Duerr, J.S., Bulow, H.E., Hobert, O., Hall, D.H., and Emmons, S.W. (2019). Whole-animal connectomes of both Caenorhabditis elegans sexes. Nature, 571(7763), 63-71, doi:10.1038/s41586-019-1352-7.

Cussat-Blanc, S., Harrington, K., & Banzhaf, W. (2019). Artificial Gene Regulatory Networks: a review. Artificial Life, 24(4), 296-328.
Dent, J.A. (1997). avr-15 encodes a chloride channel subunit that mediates inhibitory glutamatergic neurotransmission and ivermectin sensitivity in Caenorhabditis elegans. EMBO Journal, 16(19), 5867–5879.

Dvoretskii, S., Gong, Z., Gupta, A., Parent, J., & Alicea, B. (2020). Braitenberg Vehicles as Developmental Neurosimulation. In Progress.

Eichler, K., Li, F., Litwin-Kumar, A., Park, Y., Andrade, I., Schneider-Mizell, C.M., Saumweber, T., Huser, A., Eschbach, C., Gerber, B., Fetter, R.D., Truman, J.W., Priebe, C.E., Abbott, L.F., Thum, A.S., Zlatic, M., & Cardona, A. (2017). The complete connectome of a learning and memory centre in an insect brain. Nature, 548(7666), 175-182.

Faumont, S., Boulin, T., Hobert, O., & Lockery, S.R. (2006). Developmental regulation of whole cell capacitance and membrane current in identified interneurons in C. elegans. Journal of Neurophysiology, 95(6), 3665-3373. 

Fox, R.M., Von Stetina, S.E., Barlow, S.J., Shaffer, C., Olszewski, K.L., Moore, J.H., Dupuy, D., Vidal, M., & Miller, D.M. (2005). A gene expression fingerprint of C. elegans embryonic motor neurons. BMC Genomics, 6, 42.

Gao, J., Barzel, B., & Barabasi, A-L. (2016). Universal resilience patterns in complex networks. Nature, 530, 307-312.
Gendrel, M., Atlas, E.G., & Hobert, O. (2016). A cellular and regulatory map of the GABAergic nervous system of C. elegans. eLife, 5, e17686.

Gleeson, P., Lung, D., Grosu, R., Hasani, R., & Larson, S.D. (2018). c302: a multiscale framework for modelling the nervous system of Caenorhabditis elegans. Philosophical Transactions of the Royal Society B, 373, 20170379.

Goodman, M.B. (2006). Mechanosensation, WormBook. The C. elegans Research Community (eds). WormBook, doi/10.1895/wormbook.1.62.1.

Hallem, E.A. & Sternberg, P.W. (2008). Acute carbon dioxide avoidance in Caenorhabditis elegans. PNAS, 105(23), 8038-8043.
Hamblin, S. (2012). On the practical usage of genetic algorithms in ecology and evolution. Methods in Ecology and Evolution, doi:10.1111/2041-210X.12000.

Harris, T.W. Arnaboldi, V., Cain, S., Chan, J., Chen, W.J., Cho, J., Davis, P., Gao, S., Grove, C., Kishore, R., Lee, R.Y.N., Muller, H-M., Nakamura, C., Nuin, P., Paulini, M., Raciti, D., Rodgers, F., Russell, M., Schindelman, G., Van Auken, K., Wang, Q., Williams, G., Wright, A., Yook, K., Howe, K., Schedl, T., Stein, L., & Sternberg, P.W. (2019). WormBase: a modern Model Organism Information Resource. Nucleic Acids Research, gkz920, doi:10.1093/nar/gkz920.

Hobert, O., Glenwinkel, L., & White, J. (2016). Revisiting Neuronal Cell Type Classification in Caenorhabditis elegans. Current Biology, 26(22), R1197-R1203. 

Hobert O. (2016a). Terminal Selectors of Neuronal Identity. Current Topics in Developmental Biology, 116, 455-475. doi: 10.1016/bs.ctdb.2015.12.007. 

Hobert, O. (2016b). A map of terminal regulators of neuronal identity in Caenorhabditis elegans. Wiley Interdisciplinary Reviews in Developmental Biology, 5(4), 474–498.

Hobert, O. (2013). The neuronal genome of Caenorhabditis elegans. WormBook, August 13, 1-106. doi: 10.1895/wormbook.1.161.1.

Hobert, O., Johnston, R.J., & Chang, S. (2002). Left–right asymmetry in the nervous system: the Caenorhabditis elegans model. Nature Reviews Neuroscience, 3, 629–640.

Hoyle, G. (1984). The scope of neuroethology. Behavioral and Brain Sciences, 7, 367-412.

Hsieh, Y.W., Alqadah, A., & Chuang, C.F. (2014). Asymmetric neural development in the Caenorhabditis elegans olfactory system. Genesis, 52(6), 544-554. doi:10.1002/dvg.22744.

Jin, Y. & Qi, Y.B. (2018). Building stereotypic connectivity: mechanistic insights into structural plasticity from C. elegans. Current Opinion in Neurobiology, 48, 97–105.

Jorgensen, E.M. & Mango, S.E. (2002). The art and design of genetic screens: Caenorhabditis elegans. Nature Reviews Genetics, 3(5), 356-369.

Kaiser, M. (2017). Mechanisms of connectome development. Trends in Cognitive Science, 21(9), 703-717.

Kim, S., Kim, H., Kralik, J.D., & Jeong, J. (2016). Vulnerability-Based Critical Neurons, Synapses, and Pathways in the Caenorhabditis elegans Connectome. PLoS Computational Biology, 12(8), e1005084. doi:10.1371/journal.pcbi.1005084. 

Ko, H., Cossell, L., Baragli, C., Antolik, J., Clopath, C., Hofer, S.B., & Mrsic-Flogel, T.D. (2013). The emergence of functional microcircuits in visual cortex. Nature, 496(7443), 96–100.

Kratsios, P., Pinan-Lucarre, B., Kerk, S-Y., Weinreb, A., Bessereau, J-L., & Hobert, O. (2015). Transcriptional coordination of synaptogenesis and neurotransmitter signaling. Current Biology, 25(10), 1282–1295.

Mellem, J.E., Brockie, P.J., Madsen, D.M., and Maricq, A.V. (2008). Action Potentials Contribute to Neuronal Signaling in C. elegans. Nature Neuroscience, 11(8), 865–867. doi:10.1038/nn.2131.

McInnes, L., Healy, J., & Melville, J. (2018). UMAP: Uniform Manifold Approximation and Projection for Dimension Reduction. arXiv, 1802.03426.

Morck, C., Axang, C., & Pilona, M. (2003). A genetic analysis of axon guidance in the C. elegans pharynx. Developmental Biology, 260(1), 158-175.

Narayanan, D.Z. & Ghazanfar, A.A. (2014). Developmental Neuroscience: how twitches make sense. Current Biology, 24(19), R971-R972.

Nicosia, V., Vertes, P.E., Schafer, W.R., Latora, V., and Bullmore, E.T. (2013). Phase transition in the economically modeled growth of a cellular nervous system. PNAS, 110(19), 7880–7885. doi:10.1073/pnas.1300753110.

Oren-Suissa, M., Bayer, E.A., & Hobert, O. (2016). Sex-specific pruning of neuronal synapses in Caenorhabditis elegans. Nature, 533, 206–211.

Packer, J.S., Zhu, Q., Huynh, C., Sivaramakrishnan, P., Preston, E., Dueck, H., Stefanik, D., Tan, K., Trapnell, C., Kim, J., Waterston, R.H., & Murray, J.I. (2019). A lineage-resolved molecular atlas of C. elegans embryogenesis at single cell resolution. Science, 365(6459), doi:10.1126/science.aax1971.

Pereira, L., Kratsios, P., Serrano-Saiz, E., Sheftel, H., Mayo, A.E., Hall D.H., White, J.G., LeBoeuf, B., Garcia, L.R., Alon, U., & Hobert, O. (2015). A cellular and regulatory map of the cholinergic nervous system of C. elegans. eLife, 4, e12432. doi:10.7554/eLife.12432.

Picken-Bahrey, H.L. & Moody, W.J. (2003). Early Development of Voltage-Gated Ion Currents and Firing Properties in Neurons of the Mouse Cerebral Cortex. Journal of Neurophysiology, 89, 1761-1773.

Pilon, M. & Morck, C. (2005). Development of Caenorhabditis elegans pharynx, with emphasis on its nervous system. Acta Pharmacologica Sinica, 26(4), 396–404.

Portereiko, M.F. & Mango, S.E. (2001). Early morphogenesis of the Caenorhabditis elegans pharynx. Developmental Biology, 233, 482–494.

Procko, C., Lu, Y., & Shaham, S. (2011). Glia delimit shape changes of sensory neuron receptive endings in C. elegans. Development, 138, 1371–1381. 

Rothman, J. & Jarriault, S. (2019). Developmental Plasticity and Cellular Reprogramming in Caenorhabditis elegans. Genetics, 213(3), 723–757. doi:10.1534/genetics.119.302333.

Rutenberg, J., Cheng, S.M., & Levin, M. (2002). Early embryonic expression of ion channels and pumps in chick and Xenopus development. Developmental Dynamics, 225(4), 469-484.

Ryan, K., Lu1, Z., & Meinertzhagen, I.A. (2016). The CNS connectome of a tadpole larva of Ciona intestinalis (L.) highlights sidedness in the brain of a chordate sibling. eLife, 5, e16962. doi:10.7554/eLife.16962.

Salkoff, L., Wei, A.D., Baban, B., Butler, A., Fawcett, G., Ferreira, G., & Santi, C.M. (2005). Potassium channels in C. elegans (December 30), WormBook, ed. The C. elegans Research Community, WormBook, doi/10.1895/wormbook.1.42.1, http://www.wormbook.org.

Sarma, G.P., Lee, C-W., Portegys, T., Ghayoomie, V., Jacobs, T., Alicea, B., Cantarelli, M., Currie, M., Gerkin, R.C., Gingell, S., Gleeson, P., Gordon, R., Hasani, R.M., Idili, G., Khayrulin, S., Lung, D., Palyanov, A., Watts, M., & Larson, S.D. (2018). OpenWorm: overview and recent advances in integrative biological simulation of Caenorhabditis elegans. Philosophical Transactions of the Royal Society B, 373, 20170382. doi:10.1098/rstb.2017.0382.

Schafer, W.R. (2005). Deciphering the Neural and Molecular Mechanisms of C. elegans Behavior. Current Biology, 15(17), R723–R729. doi:10.1016/j.cub.2005.08.020.

Sengupta, P. & Bargmann, C.I. (1996). Cell fate specification and differentiation in the nervous system of Caenorhabditis elegans. Developmental Genetics, 18(1), 73-80.

Simaan, M. & Cruz, J.B. (1973). On the Stackelberg Strategy in Nonzero-Sum Games. Journal of Optimization Theory and Applications, 11(5), 533–555.

Sokolchik, I., Tanabe, T., Baldi, P.F., & Sze, J.Y. (2005). Polymodal sensory function of the Caenorhabditis elegans OCR-2 channel arises from distinct intrinsic determinants within the protein and is selectively conserved in mammalian TRPV proteins. Journal of Neuroscience, 25(4), 1015-1023.

Sulston, J.E., Schierenberg, E., White J.G., & Thomson, J.N. (1983). The embryonic cell lineage of the nematode Caenorhabditis elegans. Developmental Biology, 100, 64-119. 

Sulston, J.E. & Horvitz, H.R. (1977). Postembryonic cell lineages of the nematode. Caenorhabditis elegans. Developmental Biology, 56, 110-156. 
Takagi, K. (2017). A distribution model of functional connectome based on criticality and energy constraints. PLoS One, 12(5), e0177446.

Taylor, R.W., Hsieh, Y-W., Gamse, J.T., & Chuang, C-F. (2010). Making a difference together: reciprocal interactions in C. elegans and zebrafish asymmetric neural development. Development, 137(5), 681–691.

Towlson E.K., Vertes, P.E., Ahnert, S.E., Schafer, W.R., & Bullmore, E.T. (2013). The rich club of the C. elegans neuronal connectome. Journal of Neuroscience, 33(15), 6380-6387. doi: 10.1523/JNEUROSCI.3784-12.2013.

UniProt Consortium (2019). UniProt: a worldwide hub of protein knowledge. Nucleic Acids Research, 47, D506-515. https://www.uniprot.org/uniprot/Q7JPF0

Usuyama, M., Ushida, C., & Shingai, R. (2012). A Model of the Intracellular Response of an Olfactory Neuron in Caenorhabditis elegans to Odor Stimulation. PLoS One, 7(8), e42907. doi:10.1371/journal.pone.0042907.

Varier, S. & Kaiser, M. (2011). Neural Development Features: Spatio-Temporal Development of the Caenorhabditis elegans Neuronal Network. PLoS Computational Biology, l7(1), e1001044. doi:10.1371/journal.pcbi.1001044

Varshney, L.R., Chen, B.L., Paniagua, E., Hall, D.H., & Chklovskii, D.B. (2011). Structural properties of the Caenorhabditis elegans neuronal network. PLoS Computational Biology, 7(2), e1001066. https://doi.org/10.1371/journal.pcbi.1001066

Walker, D.S., Chew, Y.L., & Schafer, W.R. (2018). Genetics of Behavior in C. elegans. In "The Oxford Handbook of Invertebrate Neurobiology". J.H. Byrne ed., pgs. 1-38. Oxford University Press, Oxford, UK. doi:10.1093/oxfordhb/9780190456757.013.

Windoffer, R. & Westheide, W. (1988). The Nervous System of the Male Dinophilus gyrociliatus (Polychaeta, Dinophilidae):11. Electron Microscopical Reconstruction of Nervous Anatomy and Effector Cells. The Journal of Comparative Neurology, 272, 475-488.

White, J.G., Southgate, E., Thomson, J.N., and Brenner, S. (1986). The structure of the nervous system of the nematode Caenorhabditis elegans. Philosophical Transactions of the Royal Society B, 314(1165), 1-340. doi:10.1098/rstb.1986.0056.

White, J.G., Albertson, D.G., & Anness, M.A. (1978). Connectivity changes in a class of motoneurone during the development of a nematode. Nature, 271, 764–766.

Wu, Y., Ghitani, A., Christensen, R., Santella, A., Du, Z., Rondeau, G., Bao, Z., Colon-Ramos, D., & Shroff, H. (2011). Inverted selective plane illumination microscopy (iSPIM) enables coupled cell identity lineaging and neurodevelopmental imaging in Caenorhabditis elegans. PNAS, 108(43), 17708-17713.

Zega, G., Thorndyke, M.C., & Brown, E.R. (2006). Development of swimming behaviour in the larva of the ascidian Ciona intestinalis. The Journal of Experimental Biology, 209, 3405-3412.

Zheng, C. & Chalfie, M. (2016). Securing Neuronal Cell Fate in C. elegans. Current Topics in Developmental Biology, 116, 167-180. doi:10.1016/bs.ctdb.2015.11.011.




