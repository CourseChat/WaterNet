#---
#jupytext:
#  cell_metadata_filter: -all
#  formats: md:myst
#  text_representation:
#    extension: .md
#    format_name: myst
#    format_version: 0.13
#    jupytext_version: 1.14.4
#kernelspec:
#  display_name: Python 3 (ipykernel)
#  language: python
#  name: python3
#  
#---
---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---



# Rebuilding Water Infrastructure: Lessons For The Next Century from a Major California Water Utility

```{code-cell} python
print("Executed today", 5 + 10)
# An example input vector
x = np.array(
    [ 0.4967, -0.1383,  0.6477,  1.523 , -0.2342, -0.2341,  1.5792,
      0.7674, -0.4695,  0.5426, -0.4634, -0.4657,  0.242 , -1.9133,
      -1.7249, -0.5623, -1.0128,  0.3142, -0.908 , -1.4123,  1.4656,
      -0.2258,  0.0675, -1.4247, -0.5444,  0.1109, -1.151 ,  0.3757,
      -0.6006, -0.2917, -0.6017,  1.8523])
N = len(x)

plt.plot(x)
```

```{contents}
```
- A Research Agenda for Resilience
- University of California, Berkeley: Department of Civil Engineering
- East Bay Municipal Utility District (EBMUD)
- University of California, Berkeley: Center for Smart Infrastructure

## A Global Challenge: water utilities can no longer provide adequate water supplies without as-yet unfinanced investments in renewing and extending critical infrastructure
- Aging infrastructure presents an unanticipated requirement for capital investment: dams, reservoirs, piping, pumping, water collection systems, and water and waste water purification systems will require from two to five times more investment than today's conservative financial models anticipate. This can not be avoided or postponed. (Think Ukraine this winter) (Insert total past capital investment, total required annual rebuilding estimate; US, EU, China, India, Africa)
- Unanticipated climate change creates accelerating stress to interconnected water and energy systems. Drought, fire, and flood overwhelm existing planning models. Emergency planning fails to anticipate critical shortages.  We need a complete reexamination of water and energy infrastructure investments to prepare for a more sustainable future.
-  Political and governmental agencies fail to understand inevitable impending shortages; inadequate analysis based on out-dated tools and assumptions leads to serious policy and planning mistakes.  New tools for analysis can lead to more effective investments.
- Today's outmoded construction standards create a major legacy of unanticipated costs. Mistaking reliability for resilience means our existing infrastructure is built in a way that makes rebuilding and replacement many times too expensive. Future construction plans must immediately be re-evalutated for ease of monitoring, repair, and replacement. All past construction--every pipe segment, every pump, every tank, every valve--must be re-examined for prioritization for risk and replacement.
- New systems of high resolution satellite and drone surveillance, soil and seismic monitoring, geotechnical and hydrological testing and modeling, and sensor deployment and data acquisition from all elements of our physical plant are rapidly transforming how we manage daily operation and future design of our critical infrastructure. New data networks are orders of magnitude cheaper than past systems; new tools of machine learning and data analyis reveal new vulnerabilities and risks in real time. New materials, new methods of production, new technologies of construction, and new regulatory and reporting requirements are transforming the modern water and energy utility.
- These new capabilities create new opportunities in guiding investment in critical infrastructure. New opportunities in effective civil engineering.  Change comes slowly in critical infrastructure engineering. Innovations must be tested, over long time periods, before general adoption by those responsible for the basic functioning of modern society.
- Financial investment in infrastructure--often invisible infrastructure--comes slowly, competing with more visible human needs.  But new circumstances require new initiatives. The global workforce that creates and maintains our most critical infratructure must be given new resources, new tools,  new technologies, new organizations and a new regulatory framework.
- In a world of 8 billion people, our present systems have failed to provide basic water, power and sanitation for over two billion people. We can change that if we change how we understand what sustains our fundamental ability to live our lives. [Today's population](https://www.worldometers.info/world-population/#:~:text=World%20population%20has%20reached%208,according%20to%20the%20United%20Nations.)

## Annotated lectures given in Fall of 2022 for UC Berkeley Civil Engineering 112A: Water and Wastewater Engineering. Professor Kenichi Soga, assisted by post-doctoral students Wonjun Cha, Shi-Hung Chiu.

<br>

Thirty senior EBMUD engineers survey the design, construction, operation, maintainenance  and complete rebuilding of a one-billion-dollar-a-year critical water infrastructure serving over a million customers.

 How do new materials, new chemistries, and new  computing technologies change the design of world water infrastructure?  What is the optimal strategy to replace and rebuild existing infrastructure, often designed and built hundreds of years ago?  How does rapidly changing climate affect our designs? Our budgets? Our awareness of risks?

<br>
 The first section of lectures describe today's best practices to operate, maintain and upgrade municipal water utilities around the world. Specific examples are drawn from EBMUD, but are linked to operational practices in other utilities in California, Arizona, Nevada, Switzerland, UK, Denmark, the Netherlands, Japan, Singapore, Korea, China, Israel, Mexico, Kenya, and .....

 A major focus is on developing financial structures to anticipate the increased support needed to rebuild today's systems to meet tomorrow's needs.

 <br>
  The second section examines the challenges of aging infrastructure, and outlines policies, strategies and practices to redesign and rebuild today's installed systems, while preparing for significant unanticipated challenges from drought, fire, extremes of heat and flood, and rising sea levels that were never anticipated in the design of today's water utilities.

  <br>
  Section three outlines research priorities from major water research centers in areas such as materials, testing, real-time monitoring and control, work-force training, water quality monitoring, emergency resilience preparation, public health measures and monitoring, new machine learning tools for forecasting and prediction of system failures.

<br>

Annotations to these lectures introduce new computational interaction between class exercises and actual operating real-time data. They extend each lecture to utilize a "digital twin" model of existing and proposed infrastructure.

<br>  Research directions include machine learning, design of real-time response, materials resilience to environmental challenges, advanced water quality and treatment, and increasing the reliabiliy and security of digital models of future operating environments.

<br>
## Organization: The lectures are divided in five modules. For the purposes of this annotation, we have expanded the modules to eight chapters.
1.
- Overview of California water geography; Northern California hydrology; East Bay Municipal Utility District
2.
- Today's clean water and wastewater plant operations
-
3.
4.
5.
6.
7.
8.

For editing content, check out [the Jupyter Book documentation](https://jupyterbook.org) for more information.

Check out the content pages bundled with this sample book to see more.

```{tableofcontents}
```
