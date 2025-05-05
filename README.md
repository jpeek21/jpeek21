// Portfolio Template for HyperXite Application
// Framework: React + Tailwind CSS (Deployable on GitHub Pages)

import { useState } from 'react';

export default function Portfolio() {
  const [projects] = useState([
    {
      title: "MHD Quadcopter Research",
      timeframe: "Winter–Spring 2025",
      role: "Undergraduate Research Assistant",
      summary: `Designed and tested MHD (magnetohydrodynamic) thrusters for an underwater quadcopter propulsion system. Modeled the frame and thruster components in SolidWorks. Fabricated parts with resin printing, performed Arduino-based motor control and datalogging.`,
      tools: ["SolidWorks", "3D Resin Printing", "Arduino", "Multimeter", "Voltage Generator", "Soldering"],
      status: "Current: Designing and testing second thruster iteration",
      images: ["/img/mhd1.jpg", "/img/mhd2.jpg"]
    },
    {
      title: "MAE 106 Trench Navigation Robot",
      timeframe: "Spring 2025",
      role: "Controls & Software Lead",
      summary: `Developed an autonomous robot using hybrid control (open-loop for directional motion, closed-loop for steering via magnetometer). Programmed control logic with servo actuation and solenoid switching using MOSFETs.`,
      tools: ["Arduino Uno", "Magnetometer", "MOSFET", "SG90 Servos"],
      status: "Hardware build in progress; control logic complete.",
      images: ["/img/robot1.jpg", "/img/blockdiagram.png"]
    }
  ]);

  return (
    <main className="p-6 max-w-4xl mx-auto">
      <h1 className="text-3xl font-bold mb-4">Jonathan Peek – Engineering Portfolio</h1>
      <p className="mb-8 text-lg">UCI Mechanical Engineering Student | HyperXite Applicant | Researcher in MHD Propulsion & Controls</p>

      {projects.map((proj, i) => (
        <div key={i} className="mb-12 border-b pb-6">
          <h2 className="text-2xl font-semibold mb-1">{proj.title}</h2>
          <p className="text-sm text-gray-500 mb-2">{proj.timeframe} • {proj.role}</p>
          <p className="mb-2">{proj.summary}</p>
          <p className="mb-2 text-sm text-gray-700"><strong>Tools Used:</strong> {proj.tools.join(', ')}</p>
          <p className="mb-4 text-sm text-gray-700"><strong>Status:</strong> {proj.status}</p>
          <div className="grid grid-cols-2 gap-4">
            {proj.images.map((src, j) => (
              <img key={j} src={src} alt={`Project ${i+1} Image ${j+1}`} className="rounded-xl shadow-md" />
            ))}
          </div>
        </div>
      ))}

      <footer className="mt-12 text-sm text-gray-500">Made with ❤️ by Jonathan Peek • UCI 2025</footer>
    </main>
  );
}
