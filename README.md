<div align="center">

<h1>Primel Jayawardana</h1>

<p>CS @ University of Calgary &nbsp;&nbsp;|&nbsp;&nbsp; Systems · Robotics · Backend</p>

[![Portfolio](https://img.shields.io/badge/primelj.dev-000?style=flat-square&logo=vercel&logoColor=white)](https://primelj.dev)
&nbsp;
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/primelj)
&nbsp;
[![X](https://img.shields.io/badge/X-000000?style=flat-square&logo=x&logoColor=white)](https://x.com/PrimelJay)

</div>

<br>

I build at the infrastructure layer and ship production code.

Lately I have been building robotics systems on ROS2 and AWS: robot fleet telemetry, edge and cloud perception, language-grounded navigation, and on-robot anomaly detection. Co-founding **[Forq](https://github.com/PrimelPJ/forq)**, a food payment platform on Stripe Issuing and Flinks open banking. Previously built ML data pipelines at **ReMotion Prosthetics** on Azure, and did compliance consulting at **TechHive Advisory** across Canada, the UAE, and Europe. When I implement something, I read the paper first.

<br>

## Projects

<table>
<tr>
<td width="50%" valign="top">

**[Lexicon](https://github.com/PrimelPJ/lexicon)**

Open-vocabulary language-grounded navigation for ROS2. Say "go to the red chair" and a vision-language model (OWL-ViT) finds it, depth plus tf2 turn the pixel into a 3D map pose, and Nav2 drives there. Lifecycle nodes, a custom action interface, and inference that never blocks the executor.

`ROS2` `Nav2` `PyTorch` `OWL-ViT`

</td>
<td width="50%" valign="top">

**[Vantage](https://github.com/PrimelPJ/vantage)**

Edge and cloud object detection router for ROS2. A small model runs on the robot every frame; a per-frame policy escalates only the uncertain frames to a heavier model on an AWS SageMaker endpoint, and captures hard cases to S3 to build a retraining set.

`ROS2` `ONNX` `SageMaker` `PyTorch`

</td>
</tr>
<tr>
<td width="50%" valign="top">

**[Beacon](https://github.com/PrimelPJ/beacon)**

Robot fleet telemetry and monitoring platform. Robots stream over MQTT to AWS IoT Core, which splits into a hot path (Kinesis, Lambda, DynamoDB) for live monitoring and a cold path (Firehose, S3 Parquet, Athena) for analytics. Fully Terraformed, runs in simulation.

`ROS2` `AWS IoT` `Kinesis` `Terraform`

</td>
<td width="50%" valign="top">

**[Reflex](https://github.com/PrimelPJ/reflex)**

Learned proprioceptive anomaly detection for ROS2. An autoencoder trains on a robot's normal joint velocity and effort, exports to ONNX, and runs in a lifecycle node that publishes standard `/diagnostics`, flagging collisions, stalls, and oscillation in real time.

`ROS2` `PyTorch` `ONNX` `Autoencoder`

</td>
</tr>
</table>

<br>

## Stack

**Languages**

![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Swift](https://img.shields.io/badge/Swift-F05138?style=flat-square&logo=swift&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)
![HTML](https://img.shields.io/badge/HTML-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS-1572B6?style=flat-square&logo=css3&logoColor=white)
![R](https://img.shields.io/badge/R-276DC3?style=flat-square&logo=r&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white)

**Backend & Infrastructure**

![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=node.js&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![REST](https://img.shields.io/badge/REST-FF6C37?style=flat-square&logo=postman&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=flat-square&logo=prisma&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=flat-square&logo=supabase&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-844FBA?style=flat-square&logo=terraform&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white)
![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)
![Stripe](https://img.shields.io/badge/Stripe-635BFF?style=flat-square&logo=stripe&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=flat-square&logo=postman&logoColor=white)
![Jest](https://img.shields.io/badge/Jest-C21325?style=flat-square&logo=jest&logoColor=white)
![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)

**Frontend & Mobile**

![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![React Native](https://img.shields.io/badge/React%20Native-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![Expo](https://img.shields.io/badge/Expo-000020?style=flat-square&logo=expo&logoColor=white)
![SwiftUI](https://img.shields.io/badge/SwiftUI-F05138?style=flat-square&logo=swift&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white)

**ML & Robotics**

![ROS 2](https://img.shields.io/badge/ROS%202-22314E?style=flat-square&logo=ros&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![ONNX](https://img.shields.io/badge/ONNX-005CED?style=flat-square&logo=onnx&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat-square&logo=python&logoColor=white)
![Azure ML](https://img.shields.io/badge/Azure%20ML-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)

<br>

## Stats

<div align="center">

<img height="165" src="https://github-readme-stats.vercel.app/api?username=PrimelPJ&show_icons=true&theme=dark&hide_border=true&include_all_commits=true&count_private=true" />
<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=PrimelPJ&layout=compact&theme=dark&hide_border=true&langs_count=8" />

<br><br>

<img src="https://streak-stats.demolab.com/?user=PrimelPJ&theme=dark&hide_border=true" />

</div>

<br>

<div align="center">
  <sub>Open to SWE, systems, and robotics internships for Summer/Fall 2026 &nbsp;·&nbsp; <a href="https://primelj.dev">primelj.dev</a></sub>
</div>
