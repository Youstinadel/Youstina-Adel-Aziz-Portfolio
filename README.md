# Youstina-Adel-Aziz-Portfolio[index.html](https://github.com/user-attachments/files/22584769/index.html)
import { useState } from "react";
import { Mail, MessageCircle, Download, ArrowRight, GraduationCap, Award, Users, Briefcase, Palette, Monitor, Code, Figma, Smartphone, Globe, Calendar, MapPin, Building2, ExternalLink, Github, Send, Linkedin, Heart, Menu, X } from "lucide-react";
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Progress } from "@/components/ui/progress";
import { Badge } from "@/components/ui/badge";
import { Input } from "@/components/ui/input";
import { Textarea } from "@/components/ui/textarea";
import profileImage from "@/assets/youstina-profile.jpg";

// Navigation Component
const Navigation = () => {
  const [isMenuOpen, setIsMenuOpen] = useState(false);

  const navItems = [
    { href: "#home", label: "Home" },
    { href: "#about", label: "About" },
    { href: "#skills", label: "Skills" },
    { href: "#experience", label: "Experience" },
    { href: "#services", label: "Services" },
    { href: "#portfolio", label: "Portfolio" },
    { href: "#contact", label: "Contact" },
  ];

  const scrollToSection = (href: string) => {
    const element = document.querySelector(href);
    if (element) {
      element.scrollIntoView({ behavior: "smooth" });
    }
    setIsMenuOpen(false);
  };

  return (
    <nav className="fixed top-0 left-0 right-0 z-50 glass-nav border-b border-border/10">
      <div className="container mx-auto px-4">
        <div className="flex items-center justify-between h-16">
          <div className="flex items-center space-x-3">
            <div className="w-10 h-10 rounded-xl bg-gradient-to-r from-primary to-primary/80 flex items-center justify-center shadow-glow">
              <span className="text-white font-bold text-lg">Y</span>
            </div>
            <span className="text-xl font-bold text-hero-text">
              Youstina<span className="text-primary">.</span>
            </span>
          </div>

          <div className="hidden md:flex items-center space-x-8">
            {navItems.map((item) => (
              <button
                key={item.href}
                onClick={() => scrollToSection(item.href)}
                className="text-muted-foreground hover:text-primary transition-colors duration-300 font-medium"
              >
                {item.label}
              </button>
            ))}
          </div>

          <div className="hidden md:flex items-center space-x-4">
            <Button
              onClick={() => scrollToSection("#contact")}
              className="bg-gradient-to-r from-primary to-primary/80 hover:from-primary/90 hover:to-primary/70 text-white shadow-glow"
            >
              <Mail className="mr-2" size={16} />
              Contact Me
            </Button>
          </div>

          <button
            className="md:hidden text-hero-text"
            onClick={() => setIsMenuOpen(!isMenuOpen)}
          >
            {isMenuOpen ? <X size={24} /> : <Menu size={24} />}
          </button>
        </div>

        {isMenuOpen && (
          <div className="md:hidden absolute top-full left-0 right-0 glass-nav border-b border-border/10">
            <div className="p-4 space-y-4">
              {navItems.map((item) => (
                <button
                  key={item.href}
                  onClick={() => scrollToSection(item.href)}
                  className="block w-full text-left text-muted-foreground hover:text-primary transition-colors font-medium py-2"
                >
                  {item.label}
                </button>
              ))}
              <Button
                onClick={() => scrollToSection("#contact")}
                className="w-full bg-gradient-to-r from-primary to-primary/80 text-white mt-4"
              >
                <Mail className="mr-2" size={16} />
                Contact Me
              </Button>
            </div>
          </div>
        )}
      </div>
    </nav>
  );
};

// Hero Section Component
const HeroSection = () => {
  const scrollToContact = () => {
    const element = document.getElementById("contact");
    if (element) {
      element.scrollIntoView({ behavior: "smooth" });
    }
  };

  const scrollToPortfolio = () => {
    const element = document.getElementById("portfolio");
    if (element) {
      element.scrollIntoView({ behavior: "smooth" });
    }
  };

  return (
    <section id="home" className="min-h-screen flex items-center justify-center bg-background pt-16 relative overflow-hidden">
      <div className="absolute inset-0 bg-gradient-to-br from-primary/5 via-transparent to-secondary/5"></div>
      <div className="absolute top-1/4 left-1/4 w-72 h-72 bg-primary/10 rounded-full blur-3xl animate-float"></div>
      <div className="absolute bottom-1/4 right-1/4 w-96 h-96 bg-accent/10 rounded-full blur-3xl animate-float" style={{animationDelay: '1s'}}></div>
      
      <div className="container mx-auto px-4 relative z-10">
        <div className="grid lg:grid-cols-2 gap-12 items-center">
          <div className="space-y-8 animate-fade-in">
            <div className="space-y-6">
              <div className="space-y-2">
                <div className="inline-flex items-center px-4 py-2 rounded-full glass text-sm font-medium text-primary border">
                  ✨ Available for new projects
                </div>
                <h1 className="text-5xl md:text-7xl font-bold text-hero-text leading-tight">
                  I'M A 
                  <span className="block bg-gradient-to-r from-primary to-primary/80 bg-clip-text text-transparent">
                    UI/UX 
                    <span className="ml-4">DESIGNER</span>
                  </span>
                </h1>
              </div>
              <div className="flex items-center space-x-4">
                <div className="w-14 h-14 rounded-2xl bg-gradient-to-r from-primary to-primary/80 flex items-center justify-center shadow-glow">
                  <span className="text-white font-bold text-lg">Y</span>
                </div>
                <div className="text-sm">
                  <p className="text-hero-text font-semibold">4+ Years Experience</p>
                  <p className="text-muted-foreground">UI/UX • Graphic Design • Front-End</p>
                </div>
              </div>
            </div>

            <p className="text-lg text-muted-foreground max-w-xl">
              Passionate UI/UX designer with 4 years of experience creating intuitive, 
              user-centered designs for mobile and web platforms. Skilled in graphic design 
              and front-end development.
            </p>

            <div className="flex flex-col sm:flex-row gap-4">
              <Button 
                onClick={scrollToContact}
                className="bg-gradient-to-r from-primary to-primary/80 hover:from-primary/90 hover:to-primary/70 text-white px-8 py-6 text-lg shadow-glow transition-all duration-300 hover:scale-105"
              >
                <Mail className="mr-2" size={20} />
                Contact Me
              </Button>
              <Button 
                variant="outline" 
                onClick={scrollToPortfolio}
                className="glass border-primary/30 text-hero-text hover:bg-primary hover:text-white px-8 py-6 text-lg transition-all duration-300 hover:scale-105 group"
              >
                View Portfolio
                <ArrowRight className="ml-2 transition-transform group-hover:translate-x-1" size={20} />
              </Button>
            </div>

            <div className="flex items-center space-x-6 text-sm text-muted-foreground">
              <div className="flex items-center space-x-2">
                <div className="w-2 h-2 bg-primary rounded-full"></div>
                <span>Available for freelance</span>
              </div>
              <div className="flex items-center space-x-2">
                <div className="w-2 h-2 bg-primary rounded-full"></div>
                <span>Open to opportunities</span>
              </div>
            </div>
          </div>

          <div className="relative animate-slide-up" style={{animationDelay: '0.3s'}}>
            <div className="relative w-full max-w-md mx-auto">
              <div className="absolute -top-4 -left-4 w-20 h-20 rounded-full bg-gradient-to-r from-primary/20 to-accent/20 blur-xl animate-float"></div>
              <div className="absolute -bottom-4 -right-4 w-16 h-16 rounded-full bg-gradient-to-r from-accent/20 to-primary/20 blur-xl animate-float" style={{animationDelay: '1.5s'}}></div>
              
              <div className="relative glass-card rounded-3xl p-2 shadow-modern">
                <img 
                  src={profileImage}
                  alt="Youstina Adel Aziz - UI/UX Designer"
                  className="w-full h-auto rounded-2xl object-cover"
                />
                <div className="absolute inset-0 rounded-2xl bg-gradient-to-t from-black/20 via-transparent to-transparent"></div>
              </div>
              
              <div className="absolute -bottom-6 -right-6 glass-card p-4 rounded-2xl shadow-glow border border-primary/20 animate-glow">
                <div className="text-center">
                  <div className="text-2xl font-bold bg-gradient-to-r from-primary to-primary/80 bg-clip-text text-transparent">4+</div>
                  <div className="text-xs text-muted-foreground font-medium">Years Experience</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  );
};

// About Section Component
const AboutSection = () => {
  const highlights = [
    {
      icon: <Briefcase className="text-primary" size={24} />,
      number: "4+",
      label: "Years Experience",
    },
    {
      icon: <Users className="text-primary" size={24} />,
      number: "50+",
      label: "Projects Completed",
    },
    {
      icon: <Award className="text-primary" size={24} />,
      number: "5+",
      label: "Certificates",
    },
    {
      icon: <GraduationCap className="text-primary" size={24} />,
      number: "2",
      label: "Teaching Roles",
    },
  ];

  const skills = [
    "Figma", "Responsive Design", "Prototyping", "Visual Design",
    "Persona Creation", "User Research", "Data Analysis", "Human-Centered Design",
    "Analytical & Creative Thinking", "Collaboration", "Time Management", "Continuous Learning"
  ];

  return (
    <section id="about" className="py-20 bg-section-bg relative overflow-hidden">
      <div className="absolute inset-0 bg-gradient-to-br from-primary/5 via-transparent to-accent/5"></div>
      <div className="absolute top-0 left-1/3 w-64 h-64 bg-primary/5 rounded-full blur-3xl"></div>
      
      <div className="container mx-auto px-4 relative z-10">
        <div className="text-center mb-16 animate-fade-in">
          <div className="inline-flex items-center px-4 py-2 rounded-full glass text-sm font-medium text-primary border mb-6">
            👋 Get to know me
          </div>
          <h2 className="text-4xl md:text-5xl font-bold text-hero-text mb-4">
            About <span className="bg-gradient-to-r from-primary to-primary/80 bg-clip-text text-transparent">Me</span>
          </h2>
          <p className="text-lg text-muted-foreground max-w-2xl mx-auto">
            Passionate about creating exceptional digital experiences through thoughtful design and user research
          </p>
        </div>

        <div className="grid lg:grid-cols-2 gap-12 items-center mb-16">
          <div className="space-y-6">
            <h3 className="text-2xl font-semibold text-hero-text">Hello! I'm Youstina Adel Aziz</h3>
            <div className="space-y-4 text-muted-foreground">
              <p>
                I'm a passionate UI/UX designer with 4 years of experience creating intuitive, 
                user-centered designs for mobile and web platforms. My journey combines creative 
                design thinking with analytical problem-solving to deliver exceptional digital experiences.
              </p>
              <p>
                Currently working as a UI/UX Developer at Arpuplus, I also share my knowledge as 
                a part-time instructor at ITI and Semicorner, helping aspiring designers master 
                the fundamentals of user experience design.
              </p>
              <p>
                My expertise spans across UI/UX design, graphic design, and front-end development, 
                allowing me to bridge the gap between design and implementation. I believe in 
                continuous learning and staying updated with the latest design trends and technologies.
              </p>
            </div>
          </div>

          <div className="grid grid-cols-2 gap-6">
            {highlights.map((item, index) => (
              <Card key={index} className="glass-card text-center p-6 hover:shadow-glow transition-all duration-300 hover:scale-105 border border-border/50 group">
                <CardContent className="p-0 space-y-3">
                  <div className="flex justify-center p-3 rounded-full bg-primary/10 w-fit mx-auto group-hover:bg-primary/20 transition-colors">
                    {item.icon}
                  </div>
                  <div className="text-3xl font-bold bg-gradient-to-r from-primary to-primary/80 bg-clip-text text-transparent">{item.number}</div>
                  <div className="text-sm text-muted-foreground font-medium">{item.label}</div>
                </CardContent>
              </Card>
            ))}
          </div>
        </div>

        <div className="space-y-8">
          <h3 className="text-2xl font-semibold text-hero-text text-center">Core Skills & Competencies</h3>
          <div className="flex flex-wrap gap-3 justify-center">
            {skills.map((skill, index) => (
              <span 
                key={index}
                className="px-4 py-2 glass-card border border-primary/20 rounded-full text-sm text-foreground hover:bg-primary hover:text-white transition-all duration-300 cursor-default hover:scale-105 hover:shadow-glow"
                style={{animationDelay: `${index * 0.1}s`}}
              >
                {skill}
              </span>
            ))}
          </div>
        </div>
      </div>
    </section>
  );
};

// Skills Section Component
const SkillsSection = () => {
  const skillCategories = [
    {
      title: "UI/UX Design",
      icon: <Smartphone className="text-primary" size={32} />,
      description: "Creating intuitive and user-centered digital experiences",
      skills: [
        { name: "Figma", level: 95 },
        { name: "User Research", level: 90 },
        { name: "Prototyping", level: 88 },
        { name: "Wireframing", level: 92 },
        { name: "Design Systems", level: 85 },
      ]
    },
    {
      title: "Graphic Design",
      icon: <Palette className="text-primary" size={32} />,
      description: "Visual communication through creative design solutions",
      skills: [
        { name: "Adobe Photoshop", level: 90 },
        { name: "Adobe Illustrator", level: 88 },
        { name: "Adobe InDesign", level: 85 },
        { name: "Branding", level: 82 },
        { name: "Print Design", level: 80 },
      ]
    },
    {
      title: "Front-End Development",
      icon: <Code className="text-primary" size={32} />,
      description: "Bringing designs to life with clean, responsive code",
      skills: [
        { name: "HTML/CSS", level: 90 },
        { name: "JavaScript", level: 80 },
        { name: "React", level: 75 },
        { name: "Responsive Design", level: 95 },
        { name: "CSS Frameworks", level: 85 },
      ]
    }
  ];

  const tools = [
    { name: "Figma", icon: <Figma size={24} />, color: "bg-purple-100 text-purple-600" },
    { name: "Adobe Creative Suite", icon: <Palette size={24} />, color: "bg-red-100 text-red-600" },
    { name: "HTML/CSS", icon: <Code size={24} />, color: "bg-blue-100 text-blue-600" },
    { name: "React", icon: <Globe size={24} />, color: "bg-cyan-100 text-cyan-600" },
    { name: "Responsive Design", icon: <Monitor size={24} />, color: "bg-green-100 text-green-600" },
  ];

  return (
    <section id="skills" className="py-20 bg-background relative overflow-hidden">
      <div className="absolute inset-0 bg-gradient-to-br from-accent/5 via-transparent to-primary/5"></div>
      <div className="absolute top-0 right-1/4 w-72 h-72 bg-primary/5 rounded-full blur-3xl"></div>
      
      <div className="container mx-auto px-4 relative z-10">
        <div className="text-center mb-16 animate-fade-in">
          <div className="inline-flex items-center px-4 py-2 rounded-full glass text-sm font-medium text-primary border mb-6">
            🚀 My expertise
          </div>
          <h2 className="text-4xl md:text-5xl font-bold text-hero-text mb-4">
            My <span className="bg-gradient-to-r from-primary to-primary/80 bg-clip-text text-transparent">Skills</span>
          </h2>
          <p className="text-lg text-muted-foreground max-w-2xl mx-auto">
            A comprehensive skill set spanning design, development, and user experience
          </p>
        </div>

        <div className="grid md:grid-cols-3 gap-8 mb-16">
          {skillCategories.map((category, index) => (
            <Card key={index} className="glass-card hover:shadow-glow transition-all duration-300 hover:scale-105 border border-border/50 group" style={{animationDelay: `${index * 0.2}s`}}>
              <CardHeader className="text-center">
                <div className="flex justify-center mb-4 p-4 rounded-2xl bg-primary/10 w-fit mx-auto group-hover:bg-primary/20 transition-colors">
                  {category.icon}
                </div>
                <CardTitle className="text-xl text-hero-text group-hover:text-primary transition-colors">{category.title}</CardTitle>
                <p className="text-sm text-muted-foreground">{category.description}</p>
              </CardHeader>
              <CardContent className="space-y-4">
                {category.skills.map((skill, skillIndex) => (
                  <div key={skillIndex} className="space-y-2">
                    <div className="flex justify-between text-sm">
                      <span className="text-foreground font-medium">{skill.name}</span>
                      <span className="text-primary font-semibold">{skill.level}%</span>
                    </div>
                    <div className="relative">
                      <Progress value={skill.level} className="h-2 bg-muted" />
                      <div 
                        className="absolute top-0 left-0 h-2 bg-gradient-to-r from-primary to-primary/80 rounded-full transition-all duration-1000 ease-out"
                        style={{width: `${skill.level}%`}}
                      ></div>
                    </div>
                  </div>
                ))}
              </CardContent>
            </Card>
          ))}
        </div>

        <div className="space-y-8">
          <h3 className="text-2xl font-semibold text-hero-text text-center">Tools & Technologies</h3>
          <div className="grid grid-cols-2 md:grid-cols-5 gap-4">
            {tools.map((tool, index) => (
              <div 
                key={index}
                className="flex flex-col items-center p-6 glass-card border border-primary/20 rounded-2xl hover:shadow-glow transition-all duration-300 hover:scale-105 group"
                style={{animationDelay: `${index * 0.1}s`}}
              >
                <div className="p-3 rounded-full bg-primary/10 group-hover:bg-primary/20 transition-colors mb-3">
                  <div className="text-primary">
                    {tool.icon}
                  </div>
                </div>
                <span className="text-sm font-medium text-foreground text-center group-hover:text-primary transition-colors">{tool.name}</span>
              </div>
            ))}
          </div>
        </div>
      </div>
    </section>
  );
};

// Experience Section Component
const ExperienceSection = () => {
  const workExperience = [
    {
      title: "UI/UX Developer",
      company: "Arpuplus",
      location: "Remote",
      period: "Sep 2023 - Present",
      description: "Leading UI/UX development projects, creating responsive designs and implementing user-centered solutions for web and mobile platforms.",
      achievements: [
        "Designed and developed user interfaces for multiple client projects",
        "Collaborated with cross-functional teams to deliver seamless user experiences",
        "Implemented design systems and component libraries",
      ]
    },
    {
      title: "UI/UX Designer",
      company: "Encore Software LTD",
      location: "Hybrid",
      period: "Mar 2022 - Sep 2023",
      description: "Focused on creating intuitive user interfaces and conducting user research to improve product usability and user satisfaction.",
      achievements: [
        "Designed mobile and web applications with focus on user experience",
        "Conducted user research and usability testing",
        "Created wireframes, prototypes, and high-fidelity designs",
      ]
    },
    {
      title: "UI/UX Instructor",
      company: "ITI & Semicorner",
      location: "Part-time",
      period: "2022 - Present",
      description: "Teaching UI/UX design fundamentals and advanced concepts to aspiring designers, covering design thinking, prototyping, and user research.",
      achievements: [
        "Developed comprehensive UI/UX curriculum",
        "Mentored 100+ students in design principles",
        "Conducted workshops on design tools and methodologies",
      ]
    },
    {
      title: "Freelance UI/UX Designer",
      company: "Various Clients",
      location: "Remote",
      period: "2021 - Present",
      description: "Providing UI/UX design services for startups and small businesses, focusing on user-centered design and brand identity.",
      achievements: [
        "Completed 50+ freelance projects",
        "Specialized in mobile app and website design",
        "Built long-term client relationships",
      ]
    }
  ];

  const education = [
    {
      degree: "Bachelor's Degree in Tourism and Hotels",
      institution: "University",
      period: "Graduation: Excellent",
      description: "Strong foundation in hospitality management with excellent academic performance."
    }
  ];

  const certificates = [
    {
      name: "User Interface Design Principles",
      issuer: "EDRAK",
      date: "Jan 2025",
      type: "UI/UX Design"
    },
    {
      name: "UX Design Fundamentals Certificate",
      issuer: "ITI MAHARA-TECH",
      date: "Apr 2022",
      type: "UX Research"
    },
    {
      name: "User Experience Design Certificate",
      issuer: "EDRAK",
      date: "Jan 2022",
      type: "UX Design"
    },
    {
      name: "Graphic Design Course",
      issuer: "Roya Center",
      date: "2021",
      type: "Graphic Design",
      description: "4-month intensive course covering Photoshop, Illustrator, and InDesign"
    },
    {
      name: "Front-End Development Course",
      issuer: "Route Center",
      date: "2021",
      type: "Development",
      description: "Comprehensive course covering HTML, CSS, JavaScript, and React"
    }
  ];

  return (
    <section id="experience" className="py-20 bg-section-bg">
      <div className="container mx-auto px-4">
        <div className="text-center mb-16">
          <h2 className="text-4xl md:text-5xl font-bold text-hero-text mb-4">
            Experience & <span className="text-primary">Education</span>
          </h2>
          <p className="text-lg text-muted-foreground max-w-2xl mx-auto">
            A journey of continuous learning and professional growth in design and technology
          </p>
        </div>

        <div className="mb-16">
          <h3 className="text-2xl font-semibold text-hero-text mb-8 flex items-center">
            <Building2 className="text-primary mr-3" size={28} />
            Work Experience
          </h3>
          <div className="space-y-6">
            {workExperience.map((job, index) => (
              <Card key={index} className="hover:shadow-lg transition-shadow">
                <CardHeader>
                  <div className="flex flex-col md:flex-row md:items-center md:justify-between gap-2">
                    <div>
                      <CardTitle className="text-xl text-hero-text">{job.title}</CardTitle>
                      <p className="text-primary font-medium">{job.company}</p>
                    </div>
                    <div className="flex flex-col md:items-end gap-1">
                      <div className="flex items-center text-sm text-muted-foreground">
                        <Calendar size={16} className="mr-1" />
                        {job.period}
                      </div>
                      <div className="flex items-center text-sm text-muted-foreground">
                        <MapPin size={16} className="mr-1" />
                        {job.location}
                      </div>
                    </div>
                  </div>
                </CardHeader>
                <CardContent>
                  <p className="text-muted-foreground mb-4">{job.description}</p>
                  <ul className="space-y-2">
                    {job.achievements.map((achievement, achievementIndex) => (
                      <li key={achievementIndex} className="flex items-start">
                        <div className="w-2 h-2 bg-primary rounded-full mt-2 mr-3 flex-shrink-0"></div>
                        <span className="text-foreground text-sm">{achievement}</span>
                      </li>
                    ))}
                  </ul>
                </CardContent>
              </Card>
            ))}
          </div>
        </div>

        <div className="mb-16">
          <h3 className="text-2xl font-semibold text-hero-text mb-8 flex items-center">
            <GraduationCap className="text-primary mr-3" size={28} />
            Education
          </h3>
          <div className="space-y-6">
            {education.map((edu, index) => (
              <Card key={index} className="hover:shadow-lg transition-shadow">
                <CardHeader>
                  <CardTitle className="text-xl text-hero-text">{edu.degree}</CardTitle>
                  <p className="text-primary font-medium">{edu.institution}</p>
                  <p className="text-sm text-muted-foreground">{edu.period}</p>
                </CardHeader>
                <CardContent>
                  <p className="text-muted-foreground">{edu.description}</p>
                </CardContent>
              </Card>
            ))}
          </div>
        </div>

        <div>
          <h3 className="text-2xl font-semibold text-hero-text mb-8 flex items-center">
            <Badge className="text-primary mr-3 bg-transparent border-0 p-0" />
            Certificates & Training
          </h3>
          <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
            {certificates.map((cert, index) => (
              <Card key={index} className="hover:shadow-lg transition-shadow">
                <CardHeader>
                  <div className="flex justify-between items-start mb-2">
                    <Badge variant="secondary" className="text-xs">
                      {cert.type}
                    </Badge>
                    <span className="text-xs text-muted-foreground">{cert.date}</span>
                  </div>
                  <CardTitle className="text-lg text-hero-text leading-tight">{cert.name}</CardTitle>
                  <p className="text-primary font-medium text-sm">{cert.issuer}</p>
                </CardHeader>
                {cert.description && (
                  <CardContent>
                    <p className="text-sm text-muted-foreground">{cert.description}</p>
                  </CardContent>
                )}
              </Card>
            ))}
          </div>
        </div>
      </div>
    </section>
  );
};

// Services Section Component
const ServicesSection = () => {
  const services = [
    {
      icon: <Smartphone className="text-primary" size={48} />,
      title: "Mobile UI/UX Design",
      description: "Creating intuitive and engaging mobile app experiences with a focus on user-centered design principles and modern mobile patterns.",
      features: [
        "iOS & Android app design",
        "User research & persona creation",
        "Wireframing & prototyping",
        "Usability testing",
        "Design system creation"
      ],
      color: "from-blue-500/10 to-purple-500/10"
    },
    {
      icon: <Monitor className="text-primary" size={48} />,
      title: "Web UI/UX Design",
      description: "Designing responsive and accessible web platforms that provide exceptional user experiences across all devices and browsers.",
      features: [
        "Responsive web design",
        "User interface design",
        "Information architecture",
        "Accessibility compliance",
        "Cross-browser compatibility"
      ],
      color: "from-green-500/10 to-emerald-500/10"
    },
    {
      icon: <Palette className="text-primary" size={48} />,
      title: "Graphic Design",
      description: "Creating compelling visual communications through branding, marketing materials, and digital illustrations that capture your brand essence.",
      features: [
        "Brand identity design",
        "Marketing materials",
        "Digital illustrations",
        "Print design",
        "Social media graphics"
      ],
      color: "from-orange-500/10 to-red-500/10"
    },
    {
      icon: <Code className="text-primary" size={48} />,
      title: "Front-End Development",
      description: "Bringing designs to life with clean, performant code using modern web technologies and best practices for optimal user experiences.",
      features: [
        "HTML, CSS, JavaScript",
        "React development",
        "Responsive implementation",
        "Performance optimization",
        "Component libraries"
      ],
      color: "from-cyan-500/10 to-blue-500/10"
    },
    {
      icon: <Users className="text-primary" size={48} />,
      title: "UI/UX Consulting",
      description: "Providing expert guidance on design strategy, user experience optimization, and design process improvements for your team.",
      features: [
        "Design audits",
        "UX strategy",
        "Team training",
        "Process optimization",
        "Design system consulting"
      ],
      color: "from-purple-500/10 to-pink-500/10"
    },
    {
      icon: <Palette className="text-primary" size={48} />,
      title: "Design Workshops",
      description: "Interactive workshops and training sessions to help your team master design thinking, tools, and methodologies.",
      features: [
        "Design thinking workshops",
        "Tool training (Figma, Adobe)",
        "UX methodology training",
        "Team collaboration sessions",
        "Custom curriculum development"
      ],
      color: "from-yellow-500/10 to-orange-500/10"
    }
  ];

  const scrollToContact = () => {
    const element = document.getElementById("contact");
    if (element) {
      element.scrollIntoView({ behavior: "smooth" });
    }
  };

  return (
    <section id="services" className="py-20 bg-background">
      <div className="container mx-auto px-4">
        <div className="text-center mb-16">
          <h2 className="text-4xl md:text-5xl font-bold text-hero-text mb-4">
            My <span className="text-primary">Services</span>
          </h2>
          <p className="text-lg text-muted-foreground max-w-2xl mx-auto">
            Comprehensive design and development services to bring your digital vision to life
          </p>
        </div>

        <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-8 mb-12">
          {services.map((service, index) => (
            <Card key={index} className="hover:shadow-xl transition-all duration-300 group relative overflow-hidden">
              <div className={`absolute inset-0 bg-gradient-to-br ${service.color} opacity-0 group-hover:opacity-100 transition-opacity duration-300`}></div>
              <CardHeader className="relative z-10">
                <div className="mb-4 group-hover:scale-110 transition-transform duration-300">
                  {service.icon}
                </div>
                <CardTitle className="text-xl text-hero-text group-hover:text-primary transition-colors">
                  {service.title}
                </CardTitle>
              </CardHeader>
              <CardContent className="relative z-10">
                <p className="text-muted-foreground mb-6">{service.description}</p>
                <ul className="space-y-2">
                  {service.features.map((feature, featureIndex) => (
                    <li key={featureIndex} className="flex items-start">
                      <div className="w-2 h-2 bg-primary rounded-full mt-2 mr-3 flex-shrink-0 group-hover:scale-125 transition-transform"></div>
                      <span className="text-foreground text-sm">{feature}</span>
                    </li>
                  ))}
                </ul>
              </CardContent>
            </Card>
          ))}
        </div>

        <div className="text-center">
          <div className="mb-6">
            <h3 className="text-2xl font-semibold text-hero-text mb-4">Ready to start your project?</h3>
            <p className="text-muted-foreground max-w-xl mx-auto">
              Let's collaborate to create exceptional digital experiences that engage your users and achieve your business goals.
            </p>
          </div>
          <Button 
            onClick={scrollToContact}
            className="bg-primary hover:bg-primary/90 text-white px-8 py-6 text-lg"
          >
            Get In Touch
          </Button>
        </div>
      </div>
    </section>
  );
};

// Portfolio Section Component
const PortfolioSection = () => {
  const projects = [
    {
      title: "E-Commerce Mobile App",
      category: "Mobile UI/UX",
      description: "A comprehensive mobile shopping experience with intuitive navigation, personalized recommendations, and seamless checkout flow.",
      tools: ["Figma", "Adobe XD", "Principle"],
      image: "https://images.unsplash.com/photo-1512941937669-90a1b58e7e9c?w=600&h=400&fit=crop",
      type: "UI/UX Design",
      year: "2024"
    },
    {
      title: "SaaS Dashboard Design",
      category: "Web UI/UX",
      description: "Analytics dashboard for SaaS platform featuring data visualization, real-time metrics, and customizable widgets.",
      tools: ["Figma", "React", "D3.js"],
      image: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?w=600&h=400&fit=crop",
      type: "UI/UX Design",
      year: "2024"
    },
    {
      title: "Brand Identity Package",
      category: "Graphic Design",
      description: "Complete brand identity design including logo, color palette, typography, and brand guidelines for a tech startup.",
      tools: ["Adobe Illustrator", "Adobe Photoshop", "Adobe InDesign"],
      image: "https://images.unsplash.com/photo-1626785774573-4b799315345d?w=600&h=400&fit=crop",
      type: "Branding",
      year: "2023"
    },
    {
      title: "Healthcare App Redesign",
      category: "Mobile UI/UX",
      description: "Redesigned healthcare app focusing on accessibility, user-friendly appointment booking, and medical record management.",
      tools: ["Figma", "Miro", "UsabilityHub"],
      image: "https://images.unsplash.com/photo-1576091160399-112ba8d25d1f?w=600&h=400&fit=crop",
      type: "UI/UX Design",
      year: "2023"
    },
    {
      title: "Travel Website",
      category: "Web Development",
      description: "Responsive travel booking website with interactive maps, filtering system, and modern design implementation.",
      tools: ["React", "Tailwind CSS", "Framer Motion"],
      image: "https://images.unsplash.com/photo-1488646953014-85cb44e25828?w=600&h=400&fit=crop",
      type: "Front-End Development",
      year: "2023"
    },
    {
      title: "Restaurant App Design",
      category: "Mobile UI/UX",
      description: "Food delivery app with focus on visual appeal, easy ordering process, and real-time order tracking features.",
      tools: ["Figma", "Adobe After Effects", "InVision"],
      image: "https://images.unsplash.com/photo-1504674900247-0877df9cc836?w=600&h=400&fit=crop",
      type: "UI/UX Design",
      year: "2022"
    }
  ];

  const categories = ["All", "Mobile UI/UX", "Web UI/UX", "Graphic Design", "Web Development"];
  
  return (
    <section id="portfolio" className="py-20 bg-section-bg relative overflow-hidden">
      <div className="absolute inset-0 bg-gradient-to-br from-primary/5 via-transparent to-accent/5"></div>
      <div className="absolute bottom-0 left-1/4 w-80 h-80 bg-accent/5 rounded-full blur-3xl"></div>
      
      <div className="container mx-auto px-4 relative z-10">
        <div className="text-center mb-16 animate-fade-in">
          <div className="inline-flex items-center px-4 py-2 rounded-full glass text-sm font-medium text-primary border mb-6">
            💼 My work
          </div>
          <h2 className="text-4xl md:text-5xl font-bold text-hero-text mb-4">
            My <span className="bg-gradient-to-r from-primary to-primary/80 bg-clip-text text-transparent">Portfolio</span>
          </h2>
          <p className="text-lg text-muted-foreground max-w-2xl mx-auto">
            A showcase of my recent projects and creative work across various platforms and industries
          </p>
        </div>

        <div className="flex flex-wrap gap-4 justify-center mb-12">
          {categories.map((category, index) => (
            <Button
              key={index}
              variant={index === 0 ? "default" : "outline"}
              className={index === 0 ? "bg-primary text-white" : "hover:bg-primary hover:text-white"}
            >
              {category}
            </Button>
          ))}
        </div>

        <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-8 mb-12">
          {projects.map((project, index) => (
            <Card key={index} className="glass-card group hover:shadow-glow transition-all duration-500 overflow-hidden border border-border/50 hover:scale-105" style={{animationDelay: `${index * 0.15}s`}}>
              <div className="relative overflow-hidden">
                <img 
                  src={project.image}
                  alt={project.title}
                  className="w-full h-48 object-cover group-hover:scale-110 transition-transform duration-500"
                />
                <div className="absolute inset-0 bg-gradient-to-t from-primary/90 via-primary/50 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                  <div className="flex space-x-4 transform translate-y-4 group-hover:translate-y-0 transition-transform duration-300">
                    <Button size="icon" variant="outline" className="glass text-white hover:bg-white/20 border-white/30 hover:scale-110 transition-all">
                      <ExternalLink size={20} />
                    </Button>
                    <Button size="icon" variant="outline" className="glass text-white hover:bg-white/20 border-white/30 hover:scale-110 transition-all">
                      <Figma size={20} />
                    </Button>
                  </div>
                </div>
                <div className="absolute top-4 left-4">
                  <Badge className="bg-gradient-to-r from-primary to-primary/80 text-white border-0 shadow-glow">{project.type}</Badge>
                </div>
                <div className="absolute top-4 right-4">
                  <Badge variant="outline" className="glass text-white border-white/30">{project.year}</Badge>
                </div>
              </div>
              <CardContent className="p-6">
                <div className="mb-3">
                  <h3 className="text-xl font-semibold text-hero-text mb-1">{project.title}</h3>
                  <p className="text-primary text-sm font-medium">{project.category}</p>
                </div>
                <p className="text-muted-foreground text-sm mb-4 line-clamp-3">{project.description}</p>
                <div className="flex flex-wrap gap-2">
                  {project.tools.map((tool, toolIndex) => (
                    <span 
                      key={toolIndex}
                      className="px-2 py-1 bg-secondary text-secondary-foreground text-xs rounded-md"
                    >
                      {tool}
                    </span>
                  ))}
                </div>
              </CardContent>
            </Card>
          ))}
        </div>

        <div className="text-center">
          <div className="mb-6">
            <h3 className="text-2xl font-semibold text-hero-text mb-4">Want to see more of my work?</h3>
            <p className="text-muted-foreground max-w-xl mx-auto">
              I'm always working on new projects and exploring creative solutions. Let's connect and discuss your next project!
            </p>
          </div>
          <div className="flex flex-col sm:flex-row gap-4 justify-center">
            <Button className="bg-primary hover:bg-primary/90 text-white px-8 py-6">
              View All Projects
            </Button>
            <Button variant="outline" className="border-primary text-primary hover:bg-primary hover:text-white px-8 py-6">
              Download Portfolio
            </Button>
          </div>
        </div>
      </div>
    </section>
  );
};

// Contact Section Component
const ContactSection = () => {
  const [formData, setFormData] = useState({
    name: "",
    email: "",
    subject: "",
    message: ""
  });

  const contactInfo = [
    {
      icon: <Mail className="text-primary" size={24} />,
      title: "Email",
      value: "youstinadel9@gmail.com",
      action: "mailto:youstinadel9@gmail.com",
      description: "Send me an email anytime"
    },
    {
      icon: <MessageCircle className="text-primary" size={24} />,
      title: "WhatsApp",
      value: "+966 057 389 5601",
      action: "https://wa.me/9660573895601",
      description: "Message me on WhatsApp"
    },
    {
      icon: <MessageCircle className="text-primary" size={24} />,
      title: "WhatsApp (Alt)",
      value: "+20 100 606 9857",
      action: "https://wa.me/201006069857",
      description: "Alternative WhatsApp number"
    },
    {
      icon: <Linkedin className="text-primary" size={24} />,
      title: "LinkedIn",
      value: "linkedin.com/in/youstina-adel-",
      action: "https://www.linkedin.com/in/youstina-adel-/",
      description: "Connect with me professionally"
    }
  ];

  const handleSubmit = (e: React.FormEvent) => {
    e.preventDefault();
    console.log("Form submitted:", formData);
    setFormData({ name: "", email: "", subject: "", message: "" });
  };

  const handleInputChange = (e: React.ChangeEvent<HTMLInputElement | HTMLTextAreaElement>) => {
    const { name, value } = e.target;
    setFormData(prev => ({ ...prev, [name]: value }));
  };

  return (
    <section id="contact" className="py-20 bg-background">
      <div className="container mx-auto px-4">
        <div className="text-center mb-16">
          <h2 className="text-4xl md:text-5xl font-bold text-hero-text mb-4">
            Get In <span className="text-primary">Touch</span>
          </h2>
          <p className="text-lg text-muted-foreground max-w-2xl mx-auto">
            Ready to bring your ideas to life? Let's discuss your project and create something amazing together!
          </p>
        </div>

        <div className="grid lg:grid-cols-2 gap-12">
          <div className="space-y-8">
            <div>
              <h3 className="text-2xl font-semibold text-hero-text mb-6">Let's Connect</h3>
              <p className="text-muted-foreground mb-8">
                I'm always excited to work on new projects and collaborate with amazing people. 
                Whether you have a project in mind, need consultation, or just want to say hello, 
                I'd love to hear from you!
              </p>
            </div>

            <div className="grid gap-4">
              {contactInfo.map((info, index) => (
                <Card key={index} className="hover:shadow-lg transition-shadow">
                  <CardContent className="p-6">
                    <div className="flex items-start space-x-4">
                      <div className="flex-shrink-0">{info.icon}</div>
                      <div className="flex-1">
                        <h4 className="font-semibold text-hero-text mb-1">{info.title}</h4>
                        <p className="text-muted-foreground text-sm mb-2">{info.description}</p>
                        <a 
                          href={info.action}
                          target="_blank"
                          rel="noopener noreferrer"
                          className="text-primary hover:text-primary/80 transition-colors font-medium"
                        >
                          {info.value}
                        </a>
                      </div>
                    </div>
                  </CardContent>
                </Card>
              ))}
            </div>

            <div className="pt-8">
              <h4 className="text-lg font-semibold text-hero-text mb-4">Quick Actions</h4>
              <div className="flex flex-col sm:flex-row gap-4">
                <Button 
                  asChild
                  className="bg-primary hover:bg-primary/90 text-white"
                >
                  <a href="mailto:youstinadel9@gmail.com">
                    <Mail className="mr-2" size={20} />
                    Send Email
                  </a>
                </Button>
                <Button 
                  asChild
                  variant="outline"
                  className="border-primary text-primary hover:bg-primary hover:text-white"
                >
                  <a href="https://wa.me/9660573895601" target="_blank" rel="noopener noreferrer">
                    <MessageCircle className="mr-2" size={20} />
                    WhatsApp Me
                  </a>
                </Button>
              </div>
            </div>
          </div>

          <div>
            <Card className="shadow-lg">
              <CardHeader>
                <CardTitle className="text-2xl text-hero-text">Send Me a Message</CardTitle>
                <p className="text-muted-foreground">
                  Fill out the form below and I'll get back to you as soon as possible.
                </p>
              </CardHeader>
              <CardContent>
                <form onSubmit={handleSubmit} className="space-y-6">
                  <div className="grid md:grid-cols-2 gap-4">
                    <div>
                      <label htmlFor="name" className="block text-sm font-medium text-foreground mb-2">
                        Your Name
                      </label>
                      <Input
                        id="name"
                        name="name"
                        type="text"
                        value={formData.name}
                        onChange={handleInputChange}
                        placeholder="Enter your name"
                        required
                        className="w-full"
                      />
                    </div>
                    <div>
                      <label htmlFor="email" className="block text-sm font-medium text-foreground mb-2">
                        Email Address
                      </label>
                      <Input
                        id="email"
                        name="email"
                        type="email"
                        value={formData.email}
                        onChange={handleInputChange}
                        placeholder="Enter your email"
                        required
                        className="w-full"
                      />
                    </div>
                  </div>
                  
                  <div>
                    <label htmlFor="subject" className="block text-sm font-medium text-foreground mb-2">
                      Subject
                    </label>
                    <Input
                      id="subject"
                      name="subject"
                      type="text"
                      value={formData.subject}
                      onChange={handleInputChange}
                      placeholder="What's this about?"
                      required
                      className="w-full"
                    />
                  </div>
                  
                  <div>
                    <label htmlFor="message" className="block text-sm font-medium text-foreground mb-2">
                      Message
                    </label>
                    <Textarea
                      id="message"
                      name="message"
                      value={formData.message}
                      onChange={handleInputChange}
                      placeholder="Tell me about your project or how I can help you..."
                      required
                      rows={6}
                      className="w-full"
                    />
                  </div>
                  
                  <Button 
                    type="submit"
                    className="w-full bg-primary hover:bg-primary/90 text-white py-6 text-lg"
                  >
                    <Send className="mr-2" size={20} />
                    Send Message
                  </Button>
                </form>
              </CardContent>
            </Card>
          </div>
        </div>

        <div className="text-center mt-16">
          <Card className="max-w-2xl mx-auto bg-gradient-to-r from-primary/5 to-transparent border-primary/20">
            <CardContent className="p-8">
              <div className="flex items-center justify-center mb-4">
                <div className="w-3 h-3 bg-green-500 rounded-full mr-3 animate-pulse"></div>
                <span className="font-semibold text-hero-text">Currently Available</span>
              </div>
              <p className="text-muted-foreground">
                I'm currently accepting new projects and freelance opportunities. 
                Whether you need UI/UX design, graphic design, or front-end development services, 
                I'm ready to help bring your vision to life!
              </p>
            </CardContent>
          </Card>
        </div>
      </div>
    </section>
  );
};

// Footer Component
const Footer = () => {
  const currentYear = new Date().getFullYear();

  const scrollToTop = () => {
    window.scrollTo({ top: 0, behavior: "smooth" });
  };

  return (
    <footer className="bg-hero-text text-white py-12">
      <div className="container mx-auto px-4">
        <div className="grid md:grid-cols-3 gap-8 mb-8">
          <div className="space-y-4">
            <div className="font-bold text-2xl">
              Youstina<span className="text-primary">.</span>
            </div>
            <p className="text-gray-300 max-w-md">
              UI/UX Designer & Front-End Developer passionate about creating 
              exceptional digital experiences through thoughtful design and clean code.
            </p>
            <div className="flex space-x-4">
              <a 
                href="mailto:youstinadel9@gmail.com"
                className="w-10 h-10 bg-primary/20 rounded-full flex items-center justify-center hover:bg-primary transition-colors"
                aria-label="Email"
              >
                <Mail size={20} />
              </a>
              <a 
                href="https://wa.me/9660573895601"
                target="_blank"
                rel="noopener noreferrer"
                className="w-10 h-10 bg-primary/20 rounded-full flex items-center justify-center hover:bg-primary transition-colors"
                aria-label="WhatsApp"
              >
                <MessageCircle size={20} />
              </a>
              <a 
                href="https://www.linkedin.com/in/youstina-adel-/"
                target="_blank"
                rel="noopener noreferrer"
                className="w-10 h-10 bg-primary/20 rounded-full flex items-center justify-center hover:bg-primary transition-colors"
                aria-label="LinkedIn"
              >
                <Linkedin size={20} />
              </a>
            </div>
          </div>

          <div className="space-y-4">
            <h3 className="font-semibold text-lg">Quick Links</h3>
            <div className="grid grid-cols-2 gap-2">
              <button 
                onClick={() => document.getElementById("about")?.scrollIntoView({ behavior: "smooth" })}
                className="text-gray-300 hover:text-primary transition-colors text-left"
              >
                About Me
              </button>
              <button 
                onClick={() => document.getElementById("skills")?.scrollIntoView({ behavior: "smooth" })}
                className="text-gray-300 hover:text-primary transition-colors text-left"
              >
                Skills
              </button>
              <button 
                onClick={() => document.getElementById("experience")?.scrollIntoView({ behavior: "smooth" })}
                className="text-gray-300 hover:text-primary transition-colors text-left"
              >
                Experience
              </button>
              <button 
                onClick={() => document.getElementById("portfolio")?.scrollIntoView({ behavior: "smooth" })}
                className="text-gray-300 hover:text-primary transition-colors text-left"
              >
                Portfolio
              </button>
              <button 
                onClick={() => document.getElementById("services")?.scrollIntoView({ behavior: "smooth" })}
                className="text-gray-300 hover:text-primary transition-colors text-left"
              >
                Services
              </button>
              <button 
                onClick={() => document.getElementById("contact")?.scrollIntoView({ behavior: "smooth" })}
                className="text-gray-300 hover:text-primary transition-colors text-left"
              >
                Contact
              </button>
            </div>
          </div>

          <div className="space-y-4">
            <h3 className="font-semibold text-lg">Get In Touch</h3>
            <div className="space-y-3 text-gray-300">
              <div>
                <div className="font-medium text-white">Email</div>
                <a 
                  href="mailto:youstinadel9@gmail.com"
                  className="hover:text-primary transition-colors"
                >
                  youstinadel9@gmail.com
                </a>
              </div>
              <div>
                <div className="font-medium text-white">WhatsApp</div>
                <div className="space-y-1">
                  <a 
                    href="https://wa.me/9660573895601"
                    target="_blank"
                    rel="noopener noreferrer"
                    className="block hover:text-primary transition-colors"
                  >
                    +966 057 389 5601
                  </a>
                  <a 
                    href="https://wa.me/201006069857"
                    target="_blank"
                    rel="noopener noreferrer"
                    className="block hover:text-primary transition-colors"
                  >
                    +20 100 606 9857
                  </a>
                </div>
              </div>
              <div>
                <div className="font-medium text-white">Status</div>
                <div className="flex items-center">
                  <div className="w-2 h-2 bg-green-500 rounded-full mr-2 animate-pulse"></div>
                  <span>Available for projects</span>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div className="border-t border-gray-700 pt-8">
          <div className="flex flex-col md:flex-row justify-between items-center space-y-4 md:space-y-0">
            <div className="flex items-center text-gray-300">
              <span>© {currentYear} Youstina Adel Aziz. Made with</span>
              <Heart className="mx-2 text-primary" size={16} fill="currentColor" />
              <span>using React & Tailwind CSS</span>
            </div>
            <button 
              onClick={scrollToTop}
              className="text-gray-300 hover:text-primary transition-colors"
            >
              Back to Top ↑
            </button>
          </div>
        </div>
      </div>
    </footer>
  );
};

// Main Index Component
const Index = () => {
  return (
    <div className="min-h-screen">
      <Navigation />
      <HeroSection />
      <AboutSection />
      <SkillsSection />
      <ExperienceSection />
      <ServicesSection />
      <PortfolioSection />
      <ContactSection />
      <Footer />
    </div>
  );
};

export default Index;
