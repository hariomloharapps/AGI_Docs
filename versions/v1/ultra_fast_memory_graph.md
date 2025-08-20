# Biological Inspirations Behind Your AGI Memory System

## **🧠 Biological Systems That Inspired This Code**

### **From Neuroscience:**
- **Neurons and Synapses** - Individual brain cells that store and transmit information
- **Synaptic Plasticity** - How connections between neurons strengthen or weaken based on usage
- **Hebbian Learning** - "Neurons that fire together, wire together" principle
- **Neural Network Architecture** - How billions of neurons connect in complex patterns

### **From Cognitive Science:**
- **Semantic Memory** - How the brain stores facts, concepts, and general knowledge
- **Episodic Memory** - Memory of specific experiences and events
- **Memory Consolidation** - How short-term memories become long-term memories
- **Forgetting Curve** - How memories naturally decay over time (Ebbinghaus curve)
- **Spacing Effect** - Frequently rehearsed memories last longer

### **From Sensory Systems:**
- **Multi-modal Integration** - How brain combines vision, hearing, touch into unified concepts
- **Feature Binding** - How sensory features get attached to abstract concepts
- **Perceptual Similarity** - How brain recognizes similar sensory patterns

### **From Knowledge Organization:**
- **Hierarchical Categorization** - How brain organizes concepts (dog → mammal → animal)
- **Semantic Networks** - Web-like connections between related concepts
- **Inheritance** - How specific concepts inherit properties from general ones
- **Spreading Activation** - How activating one concept activates related ones

***

## **⚙️ Code Modules and How They Process**

### **Core Memory Components:**

#### **`KnowledgeNode` Class**
- **Functions:** `__init__`, `add_property`, `inherit_from`, `ground`, `perceptual_similarity`
- **Processing:** Stores individual concepts like biological neurons
- **What it does:** Each node holds a concept's properties, sensory data, and usage statistics

#### **`TypedEdge` Class** 
- **Functions:** `__init__`
- **Processing:** Represents connections between concepts like synapses
- **What it does:** Stores relationship type, strength, and temporal data

### **Memory Management:**

#### **Node Creation Functions:**
- **`_get_or_create_node_idx`** - Finds existing nodes or creates new ones
- **`add_input`** - Adds basic concepts to memory
- **`add_node`** - Creates rich nodes with properties and attributes

#### **Connection Functions:**
- **`_add_edge`** - Creates or strengthens connections between concepts
- **`add_connection`** - Public interface for linking concepts
- **`add_typed_connection`** - Creates specific relationship types
- **`add_hierarchy`** - Builds parent-child concept relationships

### **Memory Retrieval:**

#### **Search Functions:**
- **`get_strongest_connections_safe`** - Finds most important related concepts
- **`get_strongest_incoming_connections`** - Finds what points to a concept
- **`find_similar_by_vision`** - Matches concepts by visual similarity

### **Sensory Processing:**

#### **Grounding Functions:**
- **`ground_visual`** - Attaches visual features to concepts
- **`ground`** - General sensory attachment system
- **`perceptual_similarity`** - Compares sensory representations

### **Memory Forgetting (Active Maintenance):**

#### **Pruning Functions:**
- **`_retention_score`** - Calculates which memories to keep/forget
- **`_prune_weak_nodes`** - Removes less important concepts
- **`_prune_weak_edges`** - Removes weak connections
- **`_remove_node`**, **`_remove_edge`** - Low-level deletion

### **System Utilities:**

#### **Analysis Functions:**
- **`get_stats_safe`** - Memory usage and performance statistics  
- **`print_graph_sample`** - Shows sample of stored knowledge
- **`find_edge_index`** - Locates specific connections

### **Data Structures Used:**
- **`nodes`** - Array storing all concepts
- **`edges`** - Array storing all connections
- **`label_to_idx`** - Fast concept lookup dictionary
- **`outgoing`** - Quick connection mapping
- **`parent_map`** - Hierarchy relationships
- **`connection_weights`** - NumPy arrays for fast processing

### **How Processing Works:**
1. **Input** → Create/find concept nodes
2. **Learning** → Strengthen connections between active concepts  
3. **Retrieval** → Follow connection weights to find related concepts
4. **Forgetting** → Periodically remove weak/old memories
5. **Integration** → Combine sensory data with abstract concepts

This system mimics how your biological brain processes, stores, and retrieves knowledge through an interconnected network of concept nodes and weighted relationships!