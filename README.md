import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Phone } from "lucide-react";

const constructionSteps = [
  {
    step: "Foundation Work",
    image: "/images/foundation.jpg",
    description: "Excavation & footing work completed.",
    worker: "Raju",
    phone: "9876543210",
  },
  {
    step: "Pillar Casting",
    image: "/images/pillars.jpg",
    description: "Steel rods and concrete pillars in place.",
    worker: "Suresh",
    phone: "9123456789",
  },
];

const contacts = [
  {
    category: "Sidhanthi",
    name: "Sri Raghavendra",
    phone: "9876543210",
    note: "Vastu & muhurtham consultant",
  },
  {
    category: "Cement Trader",
    name: "JK Cement Mart",
    phone: "9123456789",
    note: "Bulk supply available",
  },
  {
    category: "Plumber",
    name: "Kiran",
    phone: "9988776655",
    note: "All bathroom fittings and piping",
  },
];

export default function ConstructionApp() {
  return (
    <div className="p-4 space-y-8">
      <h1 className="text-2xl font-bold">Construction Progress</h1>
      <div className="grid gap-4">
        {constructionSteps.map((step, index) => (
          <Card key={index}>
            <CardContent className="p-4">
              <img src={step.image} alt={step.step} className="w-full rounded-xl" />
              <h2 className="text-xl font-semibold mt-2">{step.step}</h2>
              <p>{step.description}</p>
              <p className="mt-1">👷 {step.worker}</p>
              <Button className="mt-2" variant="outline">
                <Phone className="w-4 h-4 mr-2" /> Call {step.worker}
              </Button>
            </CardContent>
          </Card>
        ))}
      </div>

      <h1 className="text-2xl font-bold mt-6">Important Contacts</h1>
      <div className="grid gap-4">
        {contacts.map((contact, index) => (
          <Card key={index}>
            <CardContent className="p-4">
              <h2 className="text-xl font-semibold">{contact.category}</h2>
              <p>👤 {contact.name}</p>
              <p>📞 {contact.phone}</p>
              <p>📝 {contact.note}</p>
              <Button className="mt-2" variant="outline">
                <Phone className="w-4 h-4 mr-2" /> Call {contact.name}
              </Button>
            </CardContent>
          </Card>
        ))}
      </div>
    </div>
  );
}
