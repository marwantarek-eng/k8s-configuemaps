# Kubernetes ConfigMaps Lab: Environment Variables and Volumes

## 📌 Task Description
This repository contains the practical implementation of a Kubernetes task involving ConfigMaps, demonstrating how to inject configuration data as both Environment Variables and mounted Volumes.

**Requirements:**
1. Create a file on your system on `/opt/cm.yaml` with specific ConfigMap content (`birke`).
2. Create a ConfigMap named `trauerweide` with content `tree=trauerweide`.
3. Create a Pod named `pod1` of image `nginx:alpine` and make key `tree` of ConfigMap `trauerweide` available as environment variable `TREE1` also Mount all keys of ConfigMap `birke` as volume. The files should be available under `/etc/birke/*`.

---

## 🚀 Step-by-Step Execution

### 1. Creating the First ConfigMap (`birke`)
A YAML file was created at `/opt/cm.yaml` and applied to generate the first ConfigMap with the required key-value pairs (`tree`, `level`, `department`).

### 2. Creating the Second ConfigMap (`trauerweide`)
The second ConfigMap was created directly via the CLI using the imperative command with the `--from-literal` flag.

### 3. Deploying the Pod (`pod1`)
A Pod manifest was generated and configured to mount the `birke` ConfigMap as a volume (at `/etc/birke`) and inject the `trauerweide` ConfigMap as an environment variable (`TREE1`). The file was then applied to the cluster.

<img width="773" height="610" alt="Screenshot 2026-04-03 105041" src="https://github.com/user-attachments/assets/d3932218-4e8b-4860-98ae-0dfcb87e57a6" />

### 4. Verification and Testing

**Checking Pod Status and Details:**
The environment variables and mounted volumes inside the running Pod were verified using the `kubectl describe pod pod1` command. The output confirms that `TREE1` is correctly mapped to the ConfigMap, and the volume is successfully mounted at `/etc/birke`.

<img width="769" height="545" alt="Screenshot 2026-04-03 105730" src="https://github.com/user-attachments/assets/e7e2ba17-ff4b-4c9a-96c3-db6aed827fb7" />

---

## 👨‍💻 Author

**Marwan Tarek**
* 📧 **Email:** [marwantarek75@gmail.com](mailto:marwantarek75@gmail.com)
* 🐙 **GitHub:** [@marwantarek-eng](https://github.com/marwantarek-eng)
