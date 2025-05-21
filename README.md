import React, { useState, useEffect } from 'react';
import { ArrowUpRight, Github, Linkedin, Mail, Globe } from 'lucide-react';

// Animated skill component with hover effects
const SkillBadge = ({ skill, color, delay }) => {
  const [isVisible, setIsVisible] = useState(false);
  
  useEffect(() => {
    const timer = setTimeout(() => {
      setIsVisible(true);
    }, delay);
    return () => clearTimeout(timer);
  }, [delay]);
  
  return (
    <div 
      className={`transform transition-all duration-500 ease-in-out ${isVisible ? 'translate-y-0 opacity-100' : 'translate-y-8 opacity-0'}`}
    >
      <div 
        className={`px-4 py-2 rounded-lg text-white font-medium m-1 shadow-lg hover:shadow-xl transition-all hover:-translate-y-1 flex items-center justify-center ${color}`}
      >
        {skill}
      </div>
    </div>
  );
};

// Animated section header
const SectionHeader = ({ title }) => {
  return (
    <div className="relative mb-8">
      <h2 className="text-3xl font-bold text-gray-800 inline-block">{title}</h2>
      <div className="h-1 w-24 bg-indigo-600 mt-2 rounded-full transform transition-all duration-300 hover:w-32"></div>
    </div>
  );
};

// Main portfolio component
const SaamPortfolio = () => {
  const [animateHeader, setAnimateHeader] = useState(false);
  
  useEffect(() => {
    setAnimateHeader(true);
  }, []);
  
  const skillCategories = [
    {
      title: "Programming Languages",
      skills: ["Python", "JavaScript", "C/C++", "SQL", "R", "HTML", "CSS"],
      colors: ["bg-blue-600", "bg-yellow-500", "bg-blue-800", "bg-orange-600", "bg-blue-500", "bg-red-500", "bg-purple-500"]
    },
    {
      title: "Libraries & Frameworks",
      skills: ["React.js", "Node.js", "scikit-learn", "Pandas", "NumPy", "TensorFlow", "Seaborn", "Matplotlib"],
      colors: ["bg-teal-500", "bg-green-600", "bg-yellow-600", "bg-green-500", "bg-blue-400", "bg-orange-500", "bg-blue-600", "bg-green-400"]
    },
    {
      title: "Developer Tools & Technologies",
      skills: ["Git/GitHub", "Postman", "Tableau", "REST APIs", "Bootstrap"],
      colors: ["bg-gray-700", "bg-orange-500", "bg-blue-500", "bg-green-600", "bg-purple-600"]
    }
  ];

  return (
    <div className="min-h-screen bg-gradient-to-br from-gray-900 to-gray-800 text-white p-8">
      {/* Header with animated intro */}
      <header className={`transition-all duration-1000 ease-out transform ${animateHeader ? 'translate-y-0 opacity-100' : '-translate-y-10 opacity-0'}`}>
        <div className="flex justify-between items-center mb-12">
          <h1 className="text-5xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500">
            Saam Sani
          </h1>
          <div className="flex space-x-4">
            <a href="https://github.com/SaamSani" className="text-gray-300 hover:text-white transition-colors">
              <Github size={24} />
            </a>
            <a href="https://linkedin.com/in/SaamSani" className="text-gray-300 hover:text-white transition-colors">
              <Linkedin size={24} />
            </a>
            <a href="mailto:ssa515@sfu.ca" className="text-gray-300 hover:text-white transition-colors">
              <Mail size={24} />
            </a>
            <a href="https://saamsani.com" className="text-gray-300 hover:text-white transition-colors">
              <Globe size={24} />
            </a>
          </div>
        </div>
        
        {/* Animated tagline */}
        <div className="mb-12 relative overflow-hidden rounded-xl bg-gradient-to-r from-blue-900 to-indigo-900 p-8 shadow-2xl">
          <div className="absolute -top-24 -right-24 h-64 w-64 rounded-full bg-blue-600 opacity-20 blur-3xl"></div>
          <div className="absolute -bottom-24 -left-24 h-64 w-64 rounded-full bg-purple-600 opacity-20 blur-3xl"></div>
          
          <h2 className="text-3xl font-bold mb-4">👋 Hi, I'm Saam</h2>
          <p className="text-xl text-gray-200 leading-relaxed">
            I'm a data-driven technology enthusiast based in <span className="font-semibold text-blue-300">Vancouver, BC</span>, 
            transforming complex problems into elegant solutions at the intersection of <span className="font-semibold text-green-300">AI</span>, 
            <span className="font-semibold text-yellow-300"> cryptocurrencies</span>, and <span className="font-semibold text-purple-300">financial markets</span>.
          </p>
        </div>
      </header>
      
      {/* About Me Section with animated background */}
      <section className="mb-16 relative overflow-hidden rounded-xl p-8 bg-gradient-to-r from-gray-800 to-gray-900 shadow-xl">
        <div className="absolute -top-40 -left-40 h-80 w-80 rounded-full bg-green-600 opacity-10 blur-3xl animate-pulse"></div>
        <div className="absolute -bottom-40 -right-40 h-80 w-80 rounded-full bg-blue-600 opacity-10 blur-3xl animate-pulse" style={{animationDelay: '2s'}}></div>
        
        <SectionHeader title="About Me" />
        <div className="space-y-6 text-lg text-gray-300 relative z-10">
          <p>
            I'm deeply fascinated by the transformative potential of <span className="font-semibold text-green-400">Artificial Intelligence</span> and its applications across different domains. 
            My expertise lies at the intersection of cutting-edge technology and practical solutions.
          </p>
          <p>
            My current focus areas include:
          </p>
          <ul className="space-y-4">
            <li className="flex items-start">
              <div className="mr-4 bg-blue-600 p-2 rounded-lg">
                <ArrowUpRight size={20} />
              </div>
              <div>
                <span className="font-semibold text-blue-300">AI for Cryptocurrency Analysis</span> — Developing predictive models and analytics tools to understand market patterns and optimize trading strategies.
              </div>
            </li>
            <li className="flex items-start">
              <div className="mr-4 bg-green-600 p-2 rounded-lg">
                <ArrowUpRight size={20} />
              </div>
              <div>
                <span className="font-semibold text-green-300">Stock Market Intelligence</span> — Building systems that leverage machine learning to forecast market movements and identify investment opportunities.
              </div>
            </li>
            <li className="flex items-start">
              <div className="mr-4 bg-purple-600 p-2 rounded-lg">
                <ArrowUpRight size={20} />
              </div>
              <div>
                <span className="font-semibold text-purple-300">AI-Powered Marketing</span> — Creating data-driven marketing solutions that optimize campaign performance through advanced analytics and automation.
              </div>
            </li>
          </ul>
          <p>
            Based in <span className="font-semibold">Vancouver</span>, I'm always open to collaborating on innovative projects that push the boundaries of what's possible with today's technology.
          </p>
        </div>
      </section>
      
      {/* Skills Section with animated badges */}
      <section className="mb-16">
        <SectionHeader title="Technical Skills" />
        
        <div className="space-y-12">
          {skillCategories.map((category, categoryIndex) => (
            <div key={categoryIndex} className="mb-8">
              <h3 className="text-xl font-semibold text-gray-300 mb-4">{category.title}</h3>
              <div className="flex flex-wrap">
                {category.skills.map((skill, index) => (
                  <SkillBadge 
                    key={index} 
                    skill={skill} 
                    color={category.colors[index % category.colors.length]} 
                    delay={300 + (index * 100) + (categoryIndex * 300)}
                  />
                ))}
              </div>
            </div>
          ))}
        </div>
      </section>
      
      {/* Contact Section */}
      <section className="rounded-xl bg-gradient-to-r from-indigo-900 to-purple-900 p-8 shadow-xl">
        <SectionHeader title="Let's Connect" />
        <p className="text-lg text-gray-200 mb-6">
          I'm always interested in new opportunities, collaborations, or just chatting about the latest in AI, crypto, or stock market trends.
        </p>
        <div className="flex flex-wrap gap-4">
          <a 
            href="mailto:ssa515@sfu.ca"
            className="flex items-center gap-2 bg-white text-indigo-900 px-6 py-3 rounded-lg font-semibold transition-all hover:shadow-lg hover:-translate-y-1"
          >
            <Mail size={20} />
            Get in Touch
          </a>
          <a 
            href="https://linkedin.com/in/SaamSani"
            className="flex items-center gap-2 bg-blue-600 text-white px-6 py-3 rounded-lg font-semibold transition-all hover:shadow-lg hover:-translate-y-1"
          >
            <Linkedin size={20} />
            Connect on LinkedIn
          </a>
          <a 
            href="https://saamsani.com"
            className="flex items-center gap-2 bg-gray-800 text-white px-6 py-3 rounded-lg font-semibold transition-all hover:shadow-lg hover:-translate-y-1"
          >
            <Globe size={20} />
            Visit Portfolio
          </a>
        </div>
      </section>
      
      {/* Footer */}
      <footer className="mt-16 text-center text-gray-400">
        <p>© {new Date().getFullYear()} Saam Sani. All rights reserved.</p>
        <p className="text-sm mt-2">Based in Vancouver, BC, Canada 🇨🇦</p>
      </footer>
    </div>
  );
};

export default SaamPortfolio;
