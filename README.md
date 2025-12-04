import { useState } from "react";

export default function App() {
  const [user, setUser] = useState(null);
  const [selectedClass, setSelectedClass] = useState(null);

  const classes = [];
  const grades = ["A", "B", "V", "D"];
  for (let i = 1; i <= 11; i++) {
    grades.forEach(g => classes.push(`${i}${g}`));
  }

  const subjects = [
    "Matematika", "Ingliz tili", "Ona tili", "Fizika", "Kimyo",
    "Biologiya", "Tarix", "Geografiya", "Informatika",
    "Musiqa", "San’at", "Sport", "Texnologiya", "IQTISOD",
    "Psixologiya", "Falsafa", "Sotsiologiya", "Fransuz tili"
  ];

  // Login UI
  if (!user) {
    return (
      <div className="flex justify-center items-center min-h-screen bg-gradient-to-br from-blue-500 to-purple-700 font-sans">
        <div className="bg-white rounded-3xl p-10 shadow-2xl w-full max-w-sm fade-in">
          <h1 className="text-3xl font-bold text-purple-900 text-center mb-6">KundalikMobile</h1>
          <input type="text" placeholder="Login" className="w-full p-3 mb-4 rounded-xl border border-gray-300 focus:outline-none"/>
          <input type="password" placeholder="Parol" className="w-full p-3 mb-4 rounded-xl border border-gray-300 focus:outline-none"/>
          <button
            onClick={() => setUser("Aziz Asadov")}
            className="w-full p-3 rounded-xl font-bold text-white bg-gradient-to-br from-purple-600 to-pink-600 hover:from-purple-700 hover:to-pink-700 transition-colors"
          >
            Kirish
          </button>
          <div className="mt-4 text-center text-white text-opacity-80 backdrop-blur-md rounded-xl p-2">
            🤖 AI avtologin yoqilgan — internet bo‘lsa avtomatik kiradi
          </div>
        </div>
      </div>
    );
  }

  // Dashboard UI
  return (
    <div className="min-h-screen p-6 bg-gradient-to-br from-blue-500 to-purple-700">
      <div className="flex justify-between items-center mb-6 text-white">
        <h1 className="text-2xl font-bold">KundalikMobile Dashboard</h1>
        <button onClick={() => { setUser(null); setSelectedClass(null); }} className="bg-red-600 p-2 rounded-lg hover:bg-red-700 transition-colors">Chiqish</button>
      </div>

      {/* Sinflar */}
      <h2 className="text-white text-xl mb-4">Sinflar</h2>
      <div className="grid grid-cols-3 sm:grid-cols-6 lg:grid-cols-8 gap-3 mb-6">
        {classes.map((c, idx) => (
          <div
            key={idx}
            onClick={() => setSelectedClass(c)}
            className={`cursor-pointer text-center p-3 rounded-xl shadow-lg font-bold text-white
              ${selectedClass === c ? "bg-purple-700" : "bg-purple-500 hover:bg-purple-600 transition-colors"}`}
          >
            {c}
          </div>
        ))}
      </div>

      {/* Tanlangan sinfning fanlari */}
      {selectedClass && (
        <div className="bg-white rounded-3xl p-6 shadow-2xl fade-in">
          <h3 className="text-purple-900 text-xl font-bold mb-4">Sinf: {selectedClass}</h3>
          <div className="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-4 gap-4">
            {subjects.map((sub, idx) => (
              <div key={idx} className="bg-pink-100 p-4 rounded-2xl shadow hover:scale-105 transition-transform">
                <h4 className="font-bold text-purple-900">{sub}</h4>
                <p className="text-gray-700 mt-1">Baholar, AI moduli, davomat shu yerda</p>
              </div>
            ))}
          </div>
        </div>
      )}
    </div>
  );
}
