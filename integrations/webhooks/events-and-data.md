# Events & Data



###

{% hint style="info" %}
When someone replies to a comment, the event 'comment.replied' is fired instead of 'submission.commented'
{% endhint %}

### submission.commented

{% code fullWidth="false" %}
```typescript
{
    projectId: string;
    projectSlug: string;
    comment: {
        id: string;
        content: string;
        user: {
            id: string;
            displayName: string;
            name: string;
            avatarUrl: string;
            loginProviderIds: {
                DISCORD: string;
            }
        },
        createdAt: Date;
    },
    submission: {
        id: string;
        user: {
            id: string;
            displayName: string;
            name: string;
            avatarUrl: string;
            loginProviderIds: {
                DISCORD: string;
            }
        },
        form: {
            id: string;
            name: string;
            slug: string;
        },
        createdAt: Date;
    }
}
```
{% endcode %}

### comment.replied

```typescript
{
    projectId: string;
    projectSlug: string;
    comment: {
        id: string;
        content: string;
        user: {
            id: string;
            displayName: string;
            name: string;
            avatarUrl: string;
            loginProviderIds: {
                DISCORD: string;
            }
        },
        parentComment: {
            id: string;
            content: string;
            user: {
                id: string;
                displayName: string;
                name: string;
                avatarUrl: string;
                loginProviderIds: {
                    DISCORD: string;
                }
            },
            createdAt: Date;
        },
        createdAt: Date;
    },
    submission: {
        id: string;
        user: {
            id: string;
            displayName: string;
            name: string;
            avatarUrl: string;
            loginProviderIds: {
                DISCORD: string;
            }
        },
        form: {
            id: string;
            title: string;
            slug: string;
        },
        createdAt: Date;
    }
}
```

### application.submitted

```typescript
{
    projectId: string;
    projectSlug: string;
    submission: {
        id: string;
        form: {
            id: string;
            title: string;
            slug: string;
        };
        answers: {
            fieldId: string;
            fieldName: string;
            value: string;
        }[];
        createdAt: Date;
    },
    user: {
        id: string;
        displayName: string;
        name: string;
        avatarUrl: string;
        loginProvidersIds: {
            DISCORD: string;
        }
    }

}
```

