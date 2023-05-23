### Hi there 👋

<!--
**RaunakSen-EE/RaunakSen-EE** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
def generate_readme(profile_info):
    readme = ""

    # Add profile image
    if 'image_url' in profile_info:
        readme += f"![Profile Image]({profile_info['image_url']})\n\n"

    # Add name and introduction
    if 'name' in profile_info:
        readme += f"# {profile_info['name']}\n\n"
    if 'introduction' in profile_info:
        readme += f"{profile_info['introduction']}\n\n"

    # Add sections
    sections = [
        {
            'title': 'Skills',
            'key': 'skills',
            'list': True
        },
        {
            'title': 'Projects',
            'key': 'projects',
            'list': True
        },
        {
            'title': 'Education',
            'key': 'education',
            'list': False
        },
        {
            'title': 'Work Experience',
            'key': 'work_experience',
            'list': False
        },
        {
            'title': 'Contact',
            'key': 'contact',
            'list': False
        }
    ]

    for section in sections:
        title = section['title']
        key = section['key']
        is_list = section['list']

        if key in profile_info:
            readme += f"## {title}\n\n"
            if is_list:
                for item in profile_info[key]:
                    readme += f"- {item}\n"
            else:
                readme += f"{profile_info[key]}\n"
            readme += "\n"

    return readme
