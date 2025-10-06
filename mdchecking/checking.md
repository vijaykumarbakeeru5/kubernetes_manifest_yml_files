
🔧 **Explanation:**
- The triple backticks (` ```bash `) start and end the code block.
- Each command inside appears on its own line.
- The `bash` after the opening backticks adds syntax highlighting.

---

Want to add comments or spacing between commands for clarity? You can do this:

```markdown
## INSTALL DOCKER ON AMAZON LINUX

```bash
# Update all packages
sudo yum update -y

# Install Docker
sudo yum install -y docker

# Start Docker service
sudo service docker start

