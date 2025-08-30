import los
from prompts import prompts

def generate_code_files(output_dir="examples"):
    if not os.path.exists(output_dir):
        os.makedirs(output_dir)
    
    for item in prompts:
        filename = f"{item['name'].replace(' ', '_')}.py"
        filepath = os.path.join(output_dir, filename)
        with open(filepath, "w")  f:
            f.write(f"# {item['name']}\n")
            f.write(f"# Language: {item['language']}\n")
            f.write(f"# Prompt: {item['prompt']}\n\n")
            f.write("# Your code goes here\n\n")
    print(f"Generated {len(prompts)} code files in '{output_dir}'.")

if __name__ == "__main__":
    generate_code_files()
