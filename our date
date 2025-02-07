import { useState } from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { motion } from "framer-motion";
import { FaHeart } from "react-icons/fa";

const dateSpots = [
  { id: 1, name: "Romantic Dinner", description: "A cozy candlelight dinner at your favorite place." },
  { id: 2, name: "Beach Walk", description: "A peaceful walk along the shore, hand in hand." },
  { id: 3, name: "Movie Night", description: "A private movie screening of your favorite film." },
  { id: 4, name: "Stargazing", description: "A dreamy night under the stars." },
];

export default function DatePlanner() {
  const [selectedSpots, setSelectedSpots] = useState([]);
  const [confirmed, setConfirmed] = useState(false);

  const toggleSpot = (spot) => {
    setSelectedSpots((prev) =>
      prev.includes(spot)
        ? prev.filter((s) => s !== spot)
        : [...prev, spot]
    );
  };

  return (
    <div className="min-h-screen bg-pink-200 flex flex-col items-center p-6 text-center">
      <motion.h1 className="text-4xl font-bold text-red-500" animate={{ scale: 1.1 }}>
        Plan Our Perfect Date ❤️
      </motion.h1>
      <div className="grid grid-cols-1 md:grid-cols-2 gap-4 mt-6">
        {dateSpots.map((spot) => (
          <motion.div key={spot.id} whileHover={{ scale: 1.05 }}>
            <Card
              className={`p-4 cursor-pointer ${selectedSpots.includes(spot) ? "bg-red-300" : "bg-white"}`}
              onClick={() => toggleSpot(spot)}
            >
              <CardContent>
                <h2 className="text-xl font-semibold">{spot.name}</h2>
                <p className="text-gray-600">{spot.description}</p>
              </CardContent>
            </Card>
          </motion.div>
        ))}
      </div>
      <Button
        className="mt-6 bg-red-500 text-white p-3 rounded-full"
        onClick={() => setConfirmed(true)}
      >
        Confirm Plan <FaHeart className="ml-2" />
      </Button>
      {confirmed && (
        <motion.div className="mt-6 p-4 bg-white rounded-xl shadow-lg" animate={{ opacity: 1 }}>
          <h2 className="text-2xl font-bold text-red-500">Your Date Plan ❤️</h2>
          <ul className="mt-2">
            {selectedSpots.map((spot, index) => (
              <li key={index} className="text-lg text-gray-700">- {spot.name}</li>
            ))}
          </ul>
        </motion.div>
      )}
    </div>
  );
}
