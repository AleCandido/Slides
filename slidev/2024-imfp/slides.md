---
theme: default
background: /assets/cover.png
title: Qibo
class: text-center
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
---

::block-component{flex="~ justify-end" w="full"}

<div m-t--30 m-r-10>
  <div text-size-5xl bg-purple w-25 transform-skew-x-30>
    <p transform-skew-x--30>Qibo</p>
  </div>

  <div bg-purple transform-skew-x-30 w-50>
    <p transform-skew-x--40>A quantum computing framework</p>
  </div>
</div>

::

---
layout: fact
---

*A bit of context...*

---

# R&D and adoption of new technologies in HEP

HEP is moving towards new technologies, in particular hardware accelerators

<div flex="~ justify-center items-center" w-full>
  <white-image src="chips.png" w="70%"/>
</div>

<div m-y-5 m-l-10>
  Moving from <span v-mark.underline.red>general purpose devices</span>
  &rArr;
  <span v-mark.circle.blue>application specific</span>
</div>

<div v-click>
  Examples of initiatives and institutions involved:

  <div flex="~ justify-center items-center gap-sm" w-full>
    <white-image src="qti.png" h-25 p-sm/>
    <white-image src="infn.png" h-25 p-sm/>
    <white-image src="biqute.png" h-25 p-sm/>
  </div>
</div>


---

::block-component{m="t-20"}
E.g.
::

<div flex="~ justify-center items-center" w-full m-t-3 m-b-8>
  <white-image src="event.png" p-sm w="70%"/>
</div>

Monte Carlo simulation and data analysis are intensive and requires lots of computing
power.

----

# Quantum computing for HEP experiments

QC4HEP WG <cite-arxiv aref="2307.03236" inline-block text-sm/>


<div grid="~ cols-2" m-y-8 class="children:(flex-(~ justify-center) gap-sm children:(rounded-xl w-80%))">
  <div>
    <img src="/assets/qc4hep-ex.png"/>
  </div>
  <div>
    <img src="/assets/qc4hep-th.png"/>
  </div>
</div>

Many experimental and theoretical HEP applications are deemed to benefit from quantum
computation.

---
layout: fact
---

*Applications*


---

<div flex="~ justify-center items-center" w-full>
  <white-image src="quantum-computing.png" w="80%" p-sm/>
</div>

---
clicks: 2
---

# Quantum machine learning


<div w-full h-full m-t--10 m-b--3 flex="~ justify-center items-center"  class="children:(absolute)">
  <white-image src="opt-1.png" w="60%" p-sm v-click="[0,1]"/>
  <white-image src="opt-2.png" w="60%" p-sm v-click="[1,2]"/>
  <white-image src="opt-3.png" w="60%" p-sm v-click="[2,3]"/>
</div>

<div text-right c-gray italic>
  credits M. Robbiati
</div>

---

# Remarks

The advantage is mainly in the inference time, and possibly ansatz expressivity.

Quantum computation is naturally based on continuous variables. But in practice they are
generated through digital control electronics with noisy calibrated pulses.

---

# qPDF

<cite-arxiv aref="2011.13934" inline-block text-sm/>


---
layout: fact
---

*Where we are*

---

# Quantum computation

Various models are proposed and explored

<br m-t-5/>

1. discrete gate-based
2. continuous variable (a.k.a. bosonic)
3. quantum annealing

<br m-t-5/>

The potential use cases partially overlap, and it is possible to emulate each other (at
least approximately).

<div text-right m-t-25>
They are particularly related to the hardware realizing them...
</div>

---

# Technologies

Many technologies simultaneously investigated <cite-arxiv aref="2304.14360"
inline-block text-sm/>

- superconducting
- ion traps
- neutral atoms
- photons
- spins in semiconductors
- NV centers in diamonds
- ...

Each with its own challenges and advantages, and investigated by different research
groups, including by private companies.

Some supports may be optimal for specific applications, and others even for further
usage, e.g. quantum memories <cite-arxiv aref="1511.04018"
inline-block text-sm/>.

---

# Superconducting

One of the platforms with most resonance

::block-component{grid="~ cols-2" w="full" gap="sm"}
  :::block-component{grid-col="start-1 end-2" bg="blue"}
    <img src="/assets/roadmap-ibm.png"/>
  :::
  :::block-component{grid-col="start-2" bg="purple"}
    <img src="/assets/roadmap-google.png"/>
  :::
::

IBM and Google are definitely two prominent players, but superconducting hardware is
being investigated by a plethora of labs.

Within the scope of this technology, many variations are also possible (flux-tunable
qubits, couplers, cross-resonance schemes), so it is a macro-category.

---

# Neutral atoms

<div flex="~ justify-center items-center" w-full>
  <img src="/assets/atom-computing.png" w="60%" rounded-lg/>
</div>

Atom computing have been the first to claim >1000 qubits <cite-arxiv aref="2401.16177" inline-block text-sm/>


---
layout: fact
---

*Quantum hardware*

---

# Control

Quantum hardware is first of all an exercise in precise control

<div grid="~ cols-2" m-y-8 class="children:(flex-(~ justify-center) gap-sm children:(rounded-xl w-80%))">
  <div>
    <img src="/assets/bit-ops.png"/>
  </div>
  <div>
    <img src="/assets/bloch-sphere-rotation.png"/>
  </div>
</div>

The quantum operation is supposed to be exact, not within a certain range.

---
layout: fact
---

*Qibo*

---
layout: full
---

# The ecosystem

<div flex="~ justify-center items-center" w-full h-full m-t--5>
  <img src="/assets/qibo_ecosystem_webpage.png" h="90%"/>
</div>

---
layout: full
---

<div flex="~ justify-center items-center" w-full h-full m-t--5 m-b-5>
  <img src="/assets/contributors.png" rounded-xl/>
</div>

<div text-right italic>
  Contributors (September 2023)
</div>

---

# Qibo <cite-arxiv aref="2009.01845" text-sm/>

Execution

<img src="/assets/backends.svg" m="t--10"/>

---

# State vector

Preserve whole information.

<div grid="~ cols-2" h="full" gap="lg" p="sm t-10 b-20" class="children:(flex-(~ col) p-sm)">
<div bg="dark:red-950 red-200">

<div flex="~ row justify-center" m="t-5 b-20">

### Challenges

</div>

- linear algebra
    - *i.e. array library*
- performances
- memory management

</div>
<div bg="dark:blue-950 blue-200">

<div flex="~ row justify-center" m="t-5 b-20">

### Approach

</div>

Adopt **widespread** and **optimized frameworks**, to benefit from their expertise
(*software reuse*).

**Chisel the last layer** on top of each framework, to mold it on our use case.

</div>
</div>

---

# Backends mechanism

Plug the framework.

<br m="2">

Structure the integration of the various libraries.

<img src="/assets/state-vector.svg"/>

Common operations are implemented once and reused (when possible).

---
clicks: 3
---

# Results <cite-arxiv aref="2203.08826 " text-sm/>

<div m--60 v-if="$slidev.nav.clicks === 1"/>
<div m--120 v-if="$slidev.nav.clicks === 2"/>
<div m--180 v-if="$slidev.nav.clicks === 3" />

<div h="full" grid="~ cols-2" gap="sm" class="children:(flex-(~ col) gap-sm children:(rounded-md p-sm bg-white))">
  <div>
    <img src="/assets/qj_qft.svg"/>
    <img src="/assets/qj_dry_vs_sim.svg"/>
    <img src="/assets/qj_qft_gpus.svg"/>
    <img src="/assets/qj-grace-managed.png"/>
  </div>
  <div>
    <img src="/assets/qj_multigpu.svg"/>
    <img src="/assets/qj_evol.svg"/>
    <img src="/assets/qj-grace-cpu.png"/>
    <img src="/assets/qj-grace-cupy.png"/>
  </div>
</div>

<h3 absolute bottom-10 left-0 z--1 p-x-20 w-full text-right>

[*on advanced hardware*](https://gist.github.com/migueldiascosta/0a0dbe061982bc4cc2bc7171785a4b86)

</h3>

---

# Automatic differentiation

for quantum machine learning (QML)


<div grid="~ cols-3" m-t-15>
<div>
  Autodiff simulation is fundamental to support QML investigation.

  A dedicated differentiable backend in simulation can considerably help algorithms
  development.

  Moving towards a single interface, encompassing both simulation and quantum hardware
  implementations.
</div>

<div col-span-2>

```mermaid
flowchart LR
  subgraph user
    tf ~~~ fw
    pt ~~~ fw
    jx ~~~ fw
  end
  tf[Tensorflow] --> qibo --> ifw["<em>e.g.</em> TensorFlow"]
  pt[PyTorch] --> qibo(((qibo)))
  jx[JAX] --> qibo
  fw[...] --> qibo
  qibo -.-> hw[Parameter shift rule]
  qibo -.-> hw1[...]
  subgraph implementation
    hw1 ~~~ ifw
    hw1 ~~~ hw
  end
```

*Framework portability: implement in one, export derivatives.*

</div>
</div>

---

# Clifford


Specialized execution.


<div h="85%" grid="~ cols-2" gap-sm>
<div>

<br m--4>

$$
    \ket{\psi} = U \ket{\psi}
$$

<div p="x-5 y-1" bg="gray-200 dark:gray-800">

**Theorem 1** *Given an n-qubit state $\ket{\psi}$, the following are
equivalent:*

<div m-l-3 text-sm>

(i) *$\ket{\psi}$ can be obtained from $\ket{0}\otimes n$ by CNOT,
Hadamard, and phase gates only.*<br>
(ii) *$\ket{\psi}$ can be obtained from $\ket{0}\otimes n$ by CNOT,
Hadamard, phase, and measurement gates only.*<br>
(iii) *$\ket{\psi}$ is stabilized by exactly 2n Pauli operators.*<br>
(iv) <span underline>***$\ket{\psi}$ is uniquely determined by $S (\ket{\psi}) = Stab
(\ket{\psi})\cap P_{n}$ or the group of Pauli operators that stabilize
$\ket{\psi}$***</span>

</div>

</div>

</div>
<div flex="~ col justify-center" text-sm>

$$
\left(
\begin{array}{ccc|ccc|c}
x_{11} & \dots & x_{1n} & z_{11} & \dots & z_{1n} & r_1 \\
\vdots & \ddots & \vdots & \vdots & \ddots & \vdots & \vdots \\
x_{n1} & \dots & x_{nn} & z_{n1} & \dots & z_{nn} & r_n \\
\hline
x_{(n+1)1} & \dots & x_{(n+1)n} & z_{(n+1)1} & \dots & z_{(n+1)n} & r_{n+1} \\
\vdots & \ddots & \vdots & \vdots & \ddots & \vdots & \vdots \\
x_{(2n)1} & \dots & x_{(2n)n} & z_{(2n)1} & \dots & z_{(2n)n} & r_{2n} \\
\end{array}
\right)
$$

Instead of operating on the whole state vector, the state is represented by a much more
compressed *tableau*.

It still requires vectorized operations on the boolean entries, that can be optimized in
a similar fashion to the general state vector approach.

</div>
</div>

---
clicks: 1
---

# Clifford

Benchmarks

<div m-t--10 h-full w-full flex="~ justify-center items-center">
  <div bg-white rounded-xl p-2>
    <img w-130 src="/assets/clifford.svg"/>
  </div>
  <div absolute w-130 h-90 bg="white op-50" rounded-xl p-2 v-click="1"/>
</div>
<p absolute top="55%" left="25%" text-15 font-600 rotate--30 c-red-700 v-click="1">Work in progress</p>

---
clicks: 3
---

# Tensor network

Optimized for observables.

<div grid="~ cols-5" gap="lg">

<div col-span-3>
<img src="/assets/quimb-circuit.svg"/>
</div>

<div col-span-2>

### Contractions

<div m-t-15 w-full flex="~ row justify-center">
<div w-50 h-50 bg-white rounded-3xl flex="~ justify-center items-center" p="l-5 t-2" class="children:(absolute w-50 h-50)">
<img src="/assets/contraction.svg" v-click="[0,1]"/>
<img src="/assets/contraction-toobad.svg" v-click="[1,2]"/>
<img src="/assets/contraction-bad.svg" v-click="[2,3]"/>
<img src="/assets/contraction-good.svg" v-click="[3,4]"/>
</div>
</div>

</div>
</div>

---
clicks: 1
---

# Tensor network 

beyond `opt_einsum`

<div grid="~ cols-2" gap="lg">
<div>

### Approximation

<div text-sm>

Based on singular value decomposition (SVD).

<div w-full flex="~ row justify-center">
<img src="/assets/mps.svg" h="50"/>
</div>

A very frequent matrix product state (MPS).

But also other ansatzes are used.

</div>

</div>
<div>

### Workload distribution

<div m-y-3 w-full flex="~ row justify-center">
<div w-90 h-40 bg-white rounded-3xl flex="~ justify-center items-center" class="children:(absolute w-70 h-50)">
<img src="/assets/tn-distribute.svg" v-click="[0,1]"/>
<img src="/assets/tn-distributed.svg" v-click="[1,2]"/>
</div>
</div>

<!-- The graph picture, on top of finding the best contractions, makes another feature -->
<!-- manifest: there are blocks of operations more self-connected than others. -->
<!---->
<!-- They could be dispatched for separate computation on distributed resources. -->

```py
for q in range(nq):
    c.apply_gate('H', q)

for q in range(0, nq, 2):
    c.apply_gate('CNOT', q, q + 1)

c.apply_gate('CNOT', 4, 7)
c.apply_gate('CNOT', 4, 1)
c.apply_gate('CNOT', 4, 0)
```

</div>
</div>

---
clicks: 1
---

# QiboTN

<div w="full" flex="~ row justify-center">
<img w="80%" bg="white" p="5 t-2" rounded="lg" src="/assets/qibotn.png"/>
<div absolute w-170 h-103 bg="white op-50" rounded-xl p-2 v-click="1"/>
</div>
<p absolute top="55%" left="25%" text-15 font-600 rotate--30 c-red-700 v-click="1">Work in progress</p>

---
layout: image-left
image: /assets/qrc-lab.png
---


<div fixed bottom-12 left-15 text-xs italic c-gray-800>
<a href="https://files-prod.tii.ae/360/TII-QRC-Computing-Lab.html">TII lab</a>
</div>

<div flex="~ col justify-center" h-full p-10>

# Qibolab <cite-arxiv aref="2308.06313" text-sm/>

Quantum control

</div>

---
transition: abrupt
---

# Qibolab - Interface

<div w="full children:90%" flex="~ justify-center row" >

```mermaid
flowchart LR
  subgraph input
    circ[Circuit] --> pulse[Pulse sequence]
  end
  pulse --> platform[Platform]
  platform --> driver[Driver] --> board[Electronics]
  subgraph physical
    board --> QPU
  end
  style input stroke:#e78,stroke-width:2px
```

</div>

<div grid="~ cols-2 rows-3" h="65%" gap-sm p="sm t-0">
<div row-span-2>

The **<span underline>input</span>** for a computation could be very standard, at the
level of a **circuit**.
That kind of interface is already defined by <span underline>Qibo</span> itself.

However, at a lower level, **pulses** are still a standard-enough way to interact with
hardware, and these are defined by <span underline>Qibolab</span>.

</div>
<div col-start-1>
    Pulse sequence plot (from notebook?)
</div>
<div row-span-3 row-start-1 col-start-2>

```python
def create():
    instrument = DummyInstrument("myinstr", "0.0.0.0:0")

    channels = ChannelMap()
    channels |= Channel(
        "readout", 
        port=instrument.ports("o1")
    )
    ...

    return Platform(
        "myplatform", 
        qubits={qubit.name: qubit}, 
        instruments={instrument.name: instrument},
        ...
    )
```

</div>
</div>

---
transition: abrupt
---

# Qibolab - Drivers

<div w="full children:90%" flex="~ justify-center row" >

```mermaid
flowchart LR
  subgraph input
    circ[Circuit] --> pulse[Pulse sequence]
  end
  pulse --> platform[Platform]
  platform --> driver[Driver] --> board[Electronics]
  subgraph physical
    board --> QPU
  end
  style physical stroke:#e78,stroke-width:2px
```

</div>

<div grid="~ cols-5" gap-sm p="sm" m-t-5>
<div flex="~ col justify-center items-center" m-t--10>
<div p="sm x-2xl" rounded bg="slate-200 dark:slate-800">

- [Qblox](https://www.qblox.com/)
- [Zurich](https://www.zhinst.com/)
- [QM](https://www.quantum-machines.co/)
- [QICK](https://github.com/openquantumhardware/qick)

</div>
</div>
<div col-span-4>

```sh
      move      1,R0        # Start at marker output channel 0 (move 1 into R0)
      nop                   # Wait a cycle for R0 to be available.

loop: set_mrk   R0          # Set marker output channels to R0
      upd_param 1000        # Update marker output channels and wait 1μs.
      asl       R0,1,R0     # Move to next marker output channel (left-shift R0).
      nop                   # Wait a cycle for R0 to be available.
      jlt       R0,16,@loop # Loop until all 4 marker output channels have been set once.

      set_mrk   0           # Reset marker output channels.
      upd_param 4           # Update marker output channels.
      stop                  # Stop sequencer.
```

<div m-t--10 z-2 relative>
<p text-right italic m-r-20>

by
[Qblox](https://qblox-qblox-instruments.readthedocs-hosted.com/en/master/cluster/q1_sequence_processor.html#example)

</p>
</div>

</div>
</div>

---

# Qibosoq - Server on QICK <cite-arxiv aref="2310.05851" text-sm/>


<div w="full children:90%" flex="~ justify-center row" >
<div flex="~ col">

```mermaid
flowchart LR
  subgraph input
    circ[Circuit] --> pulse[Pulse sequence]
  end
  pulse --> platform[Platform]
  platform <--> driver[Driver] <--> board[Electronics]
  subgraph physical
    board <--> QPU
  end
```

<div m="t--1" text-xs italic>
Qibolab handles the whole connection, and takes care of fetching the single or multiple results.
</div>
</div>
</div>

<div m-lg grid="~ cols-2" gap-sm>
<div flex="~ col justify-center">

For the single open source platform <span v="top" text-xs italic style="font-variant: small-caps">FPGA
firmware</span> currently in Qibolab, there has been a dedicate effort to define a
suitable server, to optimize the communication with the board.

<p text-right>
&xrarr; Qibosoq
</p>

</div>
<div flex="~ col items-center">
  <img src="/assets/qs-comm.svg" w="80%" p-sm rounded bg-white/>
</div>
</div>

<p absolute bottom--3 left-10 text-sm italic>

in collaboration with **INFN-UNIMIB-BIQUTE**

</p>

---

# [Platform dashboard](http://login.qrccluster.com:10000/)

<div h-full p-lg flex="~ col justify-center" gap="lg" class="children:(w-full p-lg rounded-lg bg-#111217)">
  <img src="/assets/dashboard.png"/>
  <img src="/assets/dashboard-slurm.png"/>
</div>

---

# Qibocal <cite-arxiv aref="2303.10397" inline-block text-sm/>

A due mention

<div flex="~ justify-center" h="full">
  <img src="/assets/qq_qibocal.svg" h="80%"/>
</div>

---

# Available routines

QPU control implementation

<div flex="~ justify-around" h="48%" m-t--10 m-b-5>
  <div m-t-10>
    <p>CHSH &rarr;</p>
    <p>Randomized benchmarking &darr;</p>
    <p w-100>
      They are two of the routines available in Qibocal, allowing to characterize the
      QPU performances.
    </p>
  </div>
  <white-image src="chsh.png" w="40%" p-sm/>
</div>

<div flex="~ justify-center" h="50">
  <white-image src="rb.png" w-120 p-xs/>
</div>

<!-- --- -->
<!-- layout: none -->
<!-- --- -->
<!---->
<!-- <div z--2 absolute="~" h="full" w="full" flex="~ justify-center items-center"> -->
<!---->
<!-- # [Qibocal reports](http://login.qrccluster.com:9000) -->
<!---->
<!-- </div> -->
<!---->
<!-- <iframe src="http://login.qrccluster.com:9000/" h="200%" w="200%" scale="50" translate="x--120 y--70"/> -->

---
layout: none
---

<img src="/assets/reports.png" h-full w-full/>

---
layout: none
---

<img src="/assets/reports-qutrit.png" h-full w-full/>

---
layout: end
class: text-center
---

Thanks