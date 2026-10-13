- [ ] 

## Work

> [!DO|task-progress] WORK — В работе
> ```tasks
> status.type is IN_PROGRESS
> description regex matches /\S/i
> starts on or before {{title}}
> filter by function task.file.path === query.file.path || (task.heading ?? '').toLowerCase().includes('work') || /^daily(?:\/|$)/i.test(task.file.path)
> filter by function !/(^|\/)(archive|templates)(\/|$)/i.test(task.file.path)
> filter by function !(task.tags.some(tag => /^#personal(?:\/|$)/i.test(tag)) || ['personal', 'todo.family', 'life', 'hobbies'].some(section => (task.heading ?? '').toLowerCase().includes(section)))
> filter by function !['Information', 'Idea', 'Question'].includes(task.status.name)
> hide tree
> show toolbar
> hide task count
> group by function task.tags.length > 0 ? task.tags.sort().join(", ") : "Без тегов"
> sort by function \
>   const important = task.priorityNumber <= 1; \
>   const due = task.due.moment; \
>   const urgentThrough = moment("{{title}}", "YYYY-MM-DD", true).add(1, "day"); \
>   const urgent = !!due && due.isSameOrBefore(urgentThrough, "day"); \
>   return important && urgent ? 0 : important ? 1 : urgent ? 2 : 3;
> sort by priority
> sort by due
> sort by description
> ```

> [!wait|task-waiting] WORK — Ожидаю ответа / результата
> ```tasks
> status.type is ON_HOLD
> description regex matches /\S/i
> filter by function task.file.path === query.file.path || (task.heading ?? '').toLowerCase().includes('work') || /^daily(?:\/|$)/i.test(task.file.path)
> filter by function !/(^|\/)(archive|templates)(\/|$)/i.test(task.file.path)
> filter by function !(task.tags.some(tag => /^#personal(?:\/|$)/i.test(tag)) || ['personal', 'todo.family', 'life', 'hobbies'].some(section => (task.heading ?? '').toLowerCase().includes(section)))
> filter by function !['Information', 'Idea', 'Question'].includes(task.status.name)
> hide tree
> show toolbar
> hide task count
> hide scheduled date
> hide postpone button
> group by function task.tags.length > 0 ? task.tags.sort().join(", ") : "Без тегов"
> sort by priority
> sort by description
> ```

> [!DO|task-todo] WORK — Мои действия
> ```tasks
> status.type is TODO
> description regex matches /\S/i
> starts on or before {{title}}
> filter by function task.file.path === query.file.path || (task.heading ?? '').toLowerCase().includes('work') || /^daily(?:\/|$)/i.test(task.file.path)
> filter by function !/(^|\/)(archive|templates)(\/|$)/i.test(task.file.path)
> filter by function !(task.tags.some(tag => /^#personal(?:\/|$)/i.test(tag)) || ['personal', 'todo.family', 'life', 'hobbies'].some(section => (task.heading ?? '').toLowerCase().includes(section)))
> filter by function !['Information', 'Idea', 'Question'].includes(task.status.name)
> hide tree
> show toolbar
> hide task count
> group by function task.tags.length > 0 ? task.tags.sort().join(", ") : "Без тегов"
> sort by function \
>   const important = task.priorityNumber <= 1; \
>   const due = task.due.moment; \
>   const urgentThrough = moment("{{title}}", "YYYY-MM-DD", true).add(1, "day"); \
>   const urgent = !!due && due.isSameOrBefore(urgentThrough, "day"); \
>   return important && urgent ? 0 : important ? 1 : urgent ? 2 : 3;
> sort by priority
> sort by due
> sort by description
> ```

>[!question] IDEA
>```tasks
>(description regex matches /\S/i)
>filter by function task.status.name === 'Information' || task.status.name === 'Idea' || task.status.name === 'Question' || task.status.name === 'Important'
>sort by function task.status.name == "Important" ? 0 : task.status.name == "Idea" ? 4 : task.status.name == "Information" ? 5 : 3
>sort by tag
>sort by priority
>sort by due
>sort by scheduled
>sort by description
>```

>[!success]- Finished
>```tasks
>((status.type is DONE) AND (done on {{query.file.filenameWithoutExtension}})) OR ((status.type is CANCELLED) AND (cancelled on {{query.file.filenameWithoutExtension}}))
>description regex matches /\S/i
>sort by priority
>sort by due
>sort by scheduled
>sort by description
>```

## Personal

- [ ] 

> [!TODO|task-todo] PERSONAL — Мои действия
> ```tasks
> (status.type is TODO) OR (status.type is IN_PROGRESS)
> description regex matches /\S/i
> (no happens date) OR (happens on or before {{title}})
> filter by function !/(^|\/)(archive|templates)(\/|$)/i.test(task.file.path)
> filter by function task.tags.some(tag => /^#personal(?:\/|$)/i.test(tag)) || ['personal', 'todo.family', 'life', 'hobbies'].some(section => (task.heading ?? '').toLowerCase().includes(section))
> filter by function !['Information', 'Idea', 'Question'].includes(task.status.name)
> hide tree
> show toolbar
> hide backlink
> hide task count
> group by function ['personal', 'todo.family', 'life', 'hobbies'].some(section => (task.heading ?? '').toLowerCase().includes(section)) ? task.heading : "Личное"
> sort by function task.status.name === "In Progress" ? 0 : task.status.name === "Important" ? 1 : 3
> sort by priority
> sort by happens
> sort by description
> ```

> [!wait|task-waiting] PERSONAL — Ожидаю ответа / результата
> ```tasks
> status.type is ON_HOLD
> description regex matches /\S/i
> filter by function !/(^|\/)(archive|templates)(\/|$)/i.test(task.file.path)
> filter by function task.tags.some(tag => /^#personal(?:\/|$)/i.test(tag)) || ['personal', 'todo.family', 'life', 'hobbies'].some(section => (task.heading ?? '').toLowerCase().includes(section))
> filter by function !['Information', 'Idea', 'Question'].includes(task.status.name)
> hide tree
> show toolbar
> hide backlink
> hide task count
> hide scheduled date
> hide postpone button
> group by function ['personal', 'todo.family', 'life', 'hobbies'].some(section => (task.heading ?? '').toLowerCase().includes(section)) ? task.heading : "Личное"
> sort by priority
> sort by description
> ```
