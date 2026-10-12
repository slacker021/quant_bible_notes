---
dg-publish: true
dg-home: true
---
Welcome to the *Quant's Bible*! This is an open-access repository of notes related to quantitative finance, with these notes aiming to offer a bottom-up and self-contained approach that uses pure mathematics as the language of discourse. These notes are ever-expanding and are expected to see changes as time goes by. The four fundamental topics of focuses within this intellectual repository are 
- *Pure and Applied Mathematics*
- *Mathematical Statistics*
- *Computer Science*
- *Finance and Econometrics*

Rather than treating quantitative finance as a collection of disparate facts, these notes aim to offer an interdisciplinary experience where the four disciplines are connected with one another. The author hopes that this may reduce the need for the reader to search disparate sources just to find a single fact they're interested in. 

---
# Who is this For?

### Quants, Economists, and Actuarial Scientists
First and foremost, this collection of notes was designed for those looking to become researchers in quantitative finance. While much of modern quantitative finance has become abstracted by new discoveries in mathematics, economics, and finance, as well as more powerful software packages capable of performing very complex tasks that would've taken quants of yesteryear ages to do manually, quant researchers still demand mathematical maturity. This offers quants, actuarial scientists, and economists an uncompromised approach to topics in finance that were traditionally considered to be qualitative.
### Business Majors, MBAs, and PhDs specializing in Business
Business majors with an interest in using principles of quantitative finance to better understand corporate structures will appreciate what this has to offer. While finance here is approached using the language of pure mathematics, more intuitive explanations are also provided for those who may lack the necessary quantitative skills to utilize them. MBAs and PhDs in business who're specializing in analytics or data science would also majorly appreciate this somewhat unique approach to finance in business. This reference is especially suited for those in operations management and other rigorous managerial sciences.  

### Natural Sciences and Engineering 
Third, this provides students of the engineering and sciences an alternative way to approach mathematics in the natural sciences. Most natural science courses tend to approach mathematics as a disparate collection of facts that are used as tricks. While bright students in the natural sciences can easily memorize these facts and even form intuitive connections, many are left feeling confused as to why certain rules apply in certain scenarios. Hopefully, these notes can make these facts feel more connected. Those in the natural sciences can simply read the mathematics portion of this collection, if they're not interested in the finance portion. Hopefully, this can clear up the reputation of applied mathematics feeling like a circus of tricks. 

### Mathematical Sciences
Fourth, students in the mathematical sciences would be a natural audience for this type of information. The mathematical sciences is an incredibly diverse and dynamic field, with it requiring strong mathematical maturity to truly appreciate. Those who are solely interested in the pure and applied mathematics topics may disregard the other non-math sections. The examples presented in the math sections go beyond finance. Quantitative finance has strong roots in the engineering and natural sciences, which is why examples in applied mathematics that have nothing to do with finance (at least on the surface) are provided. At the same time, this may provide those who struggle with abstract concepts a look into how mathematics works in the modern world. 

### Quant Devs and Fintech
These notes provides those who're interested in quantitative development with the theoretical grounding needed to understand the inner workings of data structures and algorithms. The increasing abstraction of software has led to many treating software like it's a black box. These notes aim to provide a strong mathematical grounding for selected topics in theoretical computer science. This provides those with backgrounds in software design a better look into how data structures and algorithms can be analyzed without looking into the concrete implementations of these theoretical concepts. 

Additionally, these notes also provide programming principles in C++ and Julia, two languages that're especially suited to the the ever-expanding field. Julia provides an easy-to-understand Syntax coupled with high performance, while C++ provides absolute software control on the hardware level without forcing the user to program in *Assembly*. 

---
# Pure and Applied Mathematics
The quantitative heart of quantitative finance has its roots in the formal and hard sciences. This knowledgebase provides a rigorous and unambiguous treatment of pure and applied mathematics, showcasing full proofs and derivations so as to provide a more rigorous and step-by-step approach. 

In providing a unified approach to pure mathematics, this knowledgebase attempts to construct its own mathematical universe. All the mathematics topics are interconnected, with backlinks in one note leading to another. This applies for the proofs and derivations for various facts, as well as topics that in different branches of mathematics that have overlap. 

As for applied mathematics, the various mathematics notes have real-world examples that provide context and examples of where these abstract notions may be applied to. Unlike pure mathematics textbooks, which are often rigorous but lacking context, and applied mathematics textbooks, which provide dynamic examples but are criticized for a lack of rigor, this collection aims to be a unified approach.

---
# Finance
Finance has evolved greatly, from a qualitative artform that was merely considered a subfield of economics or a tool in corporate studies. These notes provide a rigorous and math-based foundation for contemporary neoclassical finance. 

---
# Disclaimers and Notices

### Incomplete or Incorrect Information
This project is an ever-expanding collection of notes, and is expected to take years to become on par with what university textbooks offer. At the same time, managing and checking for mistakes is difficult due to the large amount of information stored here. Thus, feedback and corrections would be greatly appreciated. Send all concerns to ong.zach13@gmail.com. 

Overtime, more information will be added to this collection. It's likely that whatever the reader is looking for is merely something waiting to be added. 
### On Generative Artificial Intelligence
This knowledgebase makes heavy use of generative artificial intelligence, more specifically autonomous AI agents who are tasked with various roles in regulating this repository of knowledge. The agents perform the following tasks:
- **Initial Note Generation:** The original note drafts are first generated by a designated high-level agent who possesses top-level reasoning. Additionally, the agent's *temperature* setting is toned down to a very low level so as to get it to produce more predictable and deterministic results. 
- **Proofs and Derivations:** Proofs and derivations for known lemmas, propositions, and theorems are done by the same high-level agents. To ensure the proofs are correct, these agents verify the accuracy of their proofs with [Lean 4](https://lean-lang.org/). Given that the lemmas, propositions, and theorems presented here are already known to be true and have proofs scattered all over the internet, the author believes that rederiving everything from scratch is not a fruitful use of one's time.  
- **Grammar Checks:** Inspecting for grammatical errors and other minor mistakes is done by lower-level agents who require less computing power. 

##### When Not to Use AI?
The use of artificial intelligence in education remains a touchy subject that many hold strong opinions towards. While artificial intelligence is indeed powerful for automating more mundane tasks, such as finding proofs for concepts already known to be true, the author believes that the user of these notes shall refrain from using generative AI to solve specific cases of problems, conjectures, and exercises that they're trying to solve. Unlike the author's use, which is simply about having the agents add established facts, those exercises are all about the user's intellectual development. Using AI in those instances robs the learner of their ability to genuinely understand the topics presented and how to apply those topics. 

### Financial Advice and Career Assistance
This knowledge base is intended solely for learning, conceptual development, and education demonstration. While the content synthesizes sophisticated principles from diverse disciplines, it must not be interpreted or utilized as personalized financial advice, investment counsel, or a professional mandate. Financial markets are complex systems fraught with inherent risks that no theoretical model can predict nor eliminate. Therefore, all participation in investments based on this material is undertaken solely on the reader's own discretion and risk. Furthermore, any financial data that is based in reality reflects outdated market conditions.

Secondly, this knowledge base may or may not be suited for career assistance. While this provides the conceptual and practical framework for many skills and roles in quantitative finance, it lacks personalized features like exercise problems, one-on-one meetings with an instructor, interview questions, and other creature comforts that usually come with career assistance. Should a reader desire career assistance or learning how to break in to a specific niche in quantitative finance, they should seek said career assistance from someone who explicitly provides those courses. Nevertheless, this is a useful resource as the theoretical backbone and practical knowledge one may need. 

Lastly, this may provide financial literacy for those who mayn't be very literate to begin with. Financial literacy is one of the most underrated skills that one may possess today. It's not only about knowing the complexities of financial markets, but how to use the lessons gained from these notes in one's financial life. 
### Forever Free
This knowledge base was curated with explicit commitment to universal accessibility. It operates under an "open science" philosophy, meaning its contents are designed for communal learning and critical inquiry—from personal self-study modules to advanced university coursework. The synthesized material here is intended as a foundational resource for discussion. While the author encourages all forms of academic utilization, it's not intended as proprietary intellectual property for commercial or for-profit exploitation. The author believes that the advancement of knowledge in quantitative finance must remain freely accessible to the global research community. 

To maintain this mission of open access, the author doesn't solicit funds nor accept donations. The existence of this collection of research notes is predicated purely on the principle of free dissemination. Any external claim to commercialize or sell material from these notes would be contrary to the principles of this resource, and must be approached with extreme caution by anyone interested. 

---
# Technical Information
- Course content is stored in a [dedicated repository](https://github.com/slacker021/quant_bible) that's updated periodically. 
- The website displaying the information the reader is looking at right now is hosted through [Vercel](https://vercel.com/crapdosis/quant_notes) and also has its own [dedicated repository](https://github.com/slacker021/quant_notes)
- Mathematical notation is rendered with LaTex. .
- Visualizations are first rendered via a Tikz editor before being exported as images that're then included in the website. 
- Publishing control is handled with the use of the [Digital Garden](https://docs.forestry.md/) plugin for [Obsidian](https://obsidian.md/). 

---
# Philosophy of the Quant's Bible
This repository of notes follows a very different learning trajectory from most curricula presented by boot camps and university programs. Most curricula follow the *Early Transcendental* paradigm of mathematics pedagogy and education. This method of learning is primarily top-down, with an emphasis on building intuition and applying facts learned early on. Meanwhile, the rigor is usually an afterthought, and even when it's taught—it comes much later in the learner's journey. Such a method of learning is problematic because it requires the learner to pick up on the knowledge quickly and perform lots of memorization. While this works for child prodigies and other individuals who pick up on patterns quickly, other learners experience trouble and're discouraged to continue learning. 

Another paradigm of learning, which is a form of *Late Transcendental* education, takes the opposite approach: A bottom-up approach that stresses strong formalism and absolute rigor. This is the *Soviet* tradition of mathematics pedagogy that was characterized by a slow pace of learning in exchange for analytical breadth and depth. Such a paradigm ensured that the learner knew exactly what they're reading and can explain the underlying concepts. However, this paradigm easily leads to information overload. Additionally, the instructors didn't bother showing all the proofs due to the massive amount of work that entails. 

This repository aims to provide an updated version of the Soviet tradition:
- **All Proofs Shown:** All proofs are shown to ensure zero abstraction. This makes having to prove already-proven statements redundant, and instead enables the learner to focus on using these proven facts to prove more interesting facts, apply them to problems, or even make entirely new discoveries. 
- **Visual Aids:** The modules are accompanied by various graphs and visualizations to help learners picture what the phenomenon in question may look like. 
- In addition to providing readers with a rigorous but accessible mathematical foundation, such pedagogy also applies to the segments dedicated to finance, economics, computer science, and statistics. The various facts presented under them are written in the language of pure mathematics, which provides a consistent pedagogical feel as well as clear definitions for the different facts that can be deduced in these disciplines.

It's crucial to note that these notes don't attempt to reinvent the wheel or discover anything new. Instead, these notes simply aggregate already-verified facts in a coherent manner. The goal of these notes is to provide these first principles with zero abstraction so the learner can spend more time applying these concepts, and perhaps even making novel discoveries on their own. Technologies may change, markets may adapt, and new discoveries may be minted—but the foundations remain timeless. 
