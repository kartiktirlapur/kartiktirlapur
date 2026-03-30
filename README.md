import { motion } from "framer-motion";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";

export default function Portfolio() {
  return (
    <div className="min-h-screen bg-black text-white p-6">
      {/* Hero Section */}
      <motion.div
        initial={{ opacity: 0, y: -50 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 0.8 }}
        className="text-center mb-12"
      >
        <h1 className="text-5xl font-bold mb-4">Hi, I'm Kartik 👋</h1>
        <p className="text-lg text-gray-400">
          Software Engineer | Data Enthusiast | Problem Solver
        </p>
        <Button className="mt-6">View Projects</Button>
      </motion.div>

      {/* Projects Section */}
      <div className="grid md:grid-cols-3 gap-6">
        {[1, 2, 3].map((project) => (
          <motion.div
            key={project}
            whileHover={{ scale: 1.05 }}
            whileTap={{ scale: 0.95 }}
            initial={{ opacity: 0, y: 50 }}
            animate={{ opacity: 1, y: 0 }}
            transition={{ delay: project * 0.2 }}
          >
            <Card className="bg-gray-900 border-none rounded-2xl shadow-lg">
              <CardContent className="p-4">
                <h2 className="text-xl font-semibold mb-2">
                  Project {project}
                </h2>
                <p className="text-gray-400 mb-4">
                  Description of your awesome project goes here.
                </p>
                <Button variant="outline">GitHub</Button>
              </CardContent>
            </Card>
          </motion.div>
        ))}
      </div>

      {/* Footer */}
      <motion.div
        initial={{ opacity: 0 }}
        animate={{ opacity: 1 }}
        transition={{ delay: 1.5 }}
        className="text-center mt-16 text-gray-500"
      >
        © 2026 Kartik | Built with ❤️ using React & Framer Motion
      </motion.div>
    </div>
  );
}
