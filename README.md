<h1 align="center">Minimal-CV Template</h1>
<p align="center">Elegant LaTeX template for your <i>Curriculum Vitae</i><br><br>
	<img alt="AwesomeCV" src="https://github.com/jlgc96/Minimal-CV-Template/raw/master/doc/icon.png" width="250px" />
</p>

## Overview
**Minimal-CV** is a LaTeX template for a CV(Curriculum Vitae) based on a two column document, focusing on a minimal and clean design. The template provides simple commands to obtain a fully stylish document  easily. Sectioning is designed for Engineering and Programming appliances. However, this can be adapted for other types of jobs.

## How to start
If you want to start working with this template, your can download the repository using the following command:

`$ git clone https://github.com/jlgc96/Minimal-CV-Template.git`

The repository contains the following elements:
- **Doc folder**: Images for documentation.
- **Fonts folder**: The document use two fonts, [Roboto](https://fonts.google.com/specimen/Roboto) for sectioning and [Avenir LT Std](https://profont.net/family/avenir-lt-std.html) as main font.
- **Icons folder**: Two circle icons to generate skill bars. See next sections for more information.
- **Minimal-CV-example.pdf**: Generated example to show template style.
- **Minimal-CV.tex**: Main document. Commands and styles defined in the preamble are used in this file to generate the CV.
- **preamble.tex**: Commands and styles are defined in this file.
- **profile.png**: Profile picture used as example.

If your want to compile the TeX file and obtain the PDF as output, **XeLaTeX** is required. Select that compiler in your local IDE or execute the following command:

`$ xelatex Minimal-CV.tex`

## Preview

This is a preview of the output document obtained after compiling the main TeX file:

| First Page | Second page |
|:---:|:---:|
| [![](https://github.com/jlgc96/Minimal-CV-Template/raw/master/doc/Minimal-CV-example-1.png)](https://github.com/jlgc96/Minimal-CV-Template/raw/master/Minimal-CV-example.pdf)  | [![](https://github.com/jlgc96/Minimal-CV-Template/raw/master/doc/Minimal-CV-example-2.png)](https://github.com/jlgc96/Minimal-CV-Template/raw/master/Minimal-CV-example.pdf) |

## How to edit this template

In this section you can observe how the sectioning is constructed and how to edit the template with your personal data:

### Header

The top header must be fulfilled with next commands:

```
\name{Name} %Your name
\surname{Sur Name} % Your Surname
\mail{email@gmail.com} % Your email
\phone{(+34) 111 111 111} % Your phone
\address{123 Elm St.}{Fayetteville, NY} % \address{Street} {City, State, etc.)}
\github{name} % Github profile. The command is designed to automatically generate a link to your profile page.
\linkedin{Name Sur Name}{https://www.linkedin.com/} % \address{Name of your LinkedIn Profile} {Link to your profile}
\profilephoto{profile} % Insert a photo of yours.
```

Once this commands are included, you can generate automatically the header using the following instruction:

`\headgenerate`

>If you encounter some problems with the address positioning because of the width of the parameters, change the value of line 98 in the preamble.tex from #2 to #1. In future releases, I'll try to automatize this process by considering the width of the parameters and using `\ifnum` statements. However, any help is welcomed!

### Education & Courses

For this section, I've created a new environment based on `\tabularx`. The name of this environment is **edulist**. Inside this environment, you have to use a new special command named `\eduitem` which has the following parameters:

`\eduitem{Years in which you obtained the certificate}{Degree/Course/Master/etc.}{College/Institute(Place)}`

This is a simple example. Observe that the environment has a parameter where you can specify the level of the studies:
```
\begin{edulist}[Higher education]
	\eduitem{2012 - 2014}{Bachellor in the branch of Science \& Technology}{I.E.S Kantauri (Santurtzi)}
\end{edulist}

\begin{edulist}[University Studies]
	\eduitem{2014 - 2018}{Telecommunications Technology Engineering's degree (Major - Telematics)}{Escuela de Ingeniería de Bilbao (UPV-EHU)}
	\eduitem{2018 - WIP}{Master's Degree in Telecommunications Technology Engineering (Major - Telemátics)}{Escuela de Ingeniería de Bilbao (UPV-EHU)}
\end{edulist}
```
### Working Experience

This section is focused in describing the jobs you have taken. The special environment designed for this section is **worklist**. Inside it, you have to use a new command named `\workitem`. This command takes the next parameters:

`\workitem{Company}{Years of work}{Company's location}{Description of your work}`

Here I show you a little example:

```
\begin{worklist}
	\workitem{Sarenet}{September 2019 - Today}{Network Engineer}{Zamudio}{Installation
	and configuration of network equipment. Design of automated monitoring systems for such equipment. 
    Provision of services based on \textit{Cloud Computing}.}
	\separator
\end{worklist}
```

> The command `\separator`creates a simple horizontal line in the middle of the page to separate one entry from the next one. Its use is not necessary. 

### Communication Skills

In this section you can describe your capabilities with different languages. The environment created is **commlist**, which has a special command named `\commitem`. This command has the following parameters: 

`\commitem[Additional comments]{Language}{Level/Certificate}{Bar describing your skill*}`

As you can see, the last parameter will create a progress bar according to your skills (see Preview Section). The commands which define these bars are:
- `\excellent`: 5 out of 5.
- `\good`: 4 out of 5.
- `\medium`:3 out of 5.
- `\regular`: 2 out of 5.
- `\bad`: 1 out of 5.

To finish with this section, a simple example:
```
\begin{commlist}
	\commitem{Spanish}{Native Language}{\excellent}
	\commitem[(Council of Europe Level B2)]{English}{First Certificate of English}{\good}
\end{commlist}
```

### Skills Sections

This part of the CV can be highly customized according to your type of appliance. As you can appreciate on the description of the template, this one is designed for Engineering and Programming jobs. The custom environment to use in these sections is **skilllist**. The command to add new entries will be `\skillitem`:

`\skillitem{Task/Element}{Description/Projects done}{Bar describing your skill*}`

The progress bar generate in the last parameter is the same as the one seen in the previous section. An example could be:
```
\begin{skilllist} [Programming Language]
	\skillitem{C}{Medium knowledge. Low-level code control.}{\medium}
	\skillitem{Python}{Medium knowledge. Learning how to program SDN Controllers.}{\medium}
\end{skilllist}
```
>Note: The environment has a paremeter to introduce the topic of your skills.

### Additional information 

In the last section of the CV you can introduce additional information about yourself. The design of this section is minimum. A modified `\itemize` is provided in other to satisfy the template style, but no other changes where made. This new environment is called **extralist** and you only need to use `\item{}` to add new bullets to the list.

```
\begin{extralist}
	\item{Your information}
\end{extralist}
```
## Main Contributors
- Jose Luis González Calvo 

## Credits
[Awesome-CV](https://github.com/posquit0/Awesome-CV) template for the header idea and [TCCV](https://github.com/ntd/tccv/) template for the two-column document basis. 
